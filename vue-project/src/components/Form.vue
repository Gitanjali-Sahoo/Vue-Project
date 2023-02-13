<template>
    <div id="card-wrapper">
        <div id="visa">
            <!-- <h2 id="log-in">Log In</h2> -->
            <h2 id="log-in">{{ message }}</h2>
            <input
                class="btn btn-outline-secondary"
                type="button"
                value="Sign in with Google"
            />
            <h4>---------------Or---------------</h4>
            <p>
                Please enter your Username, email and password to access your
                account.
            </p>

            <form @submit.prevent="handleSubmission">
                <label for="full name" class="form-lbl">Full Name:</label>
                <input class="form-input" type="text" v-model="name" required />
                <br />
                <label for="email" class="form-lbl">Email Address:</label>
                <input
                    class="form-input"
                    type="text"
                    v-model="email"
                    required
                />
                <br />
                <span v-if="msg.email">{{ msg.email }}</span>
                <label for="password" class="form-lbl">Password:</label>
                <input
                    class="form-input"
                    type="text"
                    v-model="password"
                    required
                /><br />
                <span v-if="msg.password">{{ msg.password }}</span>

                <input
                    class="btn btn-light"
                    type="submit"
                    :disabled="!disabled.every((i) => i === false)"
                />
            </form>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Test',
        data() {
            return {
                message: this.text,
                name: '',
                password: '',
                email: '',
                msg: [],

                disabled: [true, true]
            }
        },
        props: {
            text: {
                type: String,
                default: 'Log In'
            }
        },
        watch: {
            email(value) {
                this.validateEmail(value)
            },
            password(value) {
                this.validatePassword(value)
            }
        },
        methods: {
            validateEmail(value) {
                if (
                    /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(value)
                ) {
                    this.msg['email'] = ''
                    this.disabled = [false, this.disabled[1]]
                } else {
                    this.msg['email'] = 'Invalid Email Address'
                    this.disabled = [true, this.disabled[1]]
                }
            },
            validatePassword(value) {
                let difference = 8 - value.length
                if (value.length < 8) {
                    this.msg['password'] =
                        'Must be 5 characters! ' +
                        difference +
                        ' characters left'
                    this.disabled = [this.disabled[1], true]
                } else {
                    this.msg['password'] = ''
                    this.disabled = [this.disabled[1], false]
                }
            },
            handleSubmission() {
                alert('Thank You. Now you are logged in')
                
            }
        }
    }
</script>

<style scoped>
    #card-wrapper {
        z-index: 1;
        /* background-color: rgb(194, 215, 245); */
        background-color: rgb(196, 196, 192);
        max-width: 941px;
        margin: 0, auto;
        width: 100%;
        border-radius: 5px;

        justify-content: center;
        align-items: center;
        margin-left: 10%;
    }
    #visa {
        margin: 20px;
    }
    #log-in {
        margin-bottom: 20px;
        font-weight: bold;
        color: #6c757d;
    }
    .btn {
        margin-bottom: 20px;
    }

    .form-input {
        display: block;
        width: 400px;

        padding: 0.375rem 0.75rem;
        font-size: 1rem;
        font-weight: 400;
        line-height: 1.5;
        color: #212529;
        background-color: #fff;
        background-clip: padding-box;
        border: 1px solid #ced4da;
        -webkit-appearance: none;
        -moz-appearance: none;
        appearance: none;
        border-radius: 0.375rem;
        transition: border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
    }
    .form-lbl {
        margin-bottom: 0.5rem;
    }
</style>
