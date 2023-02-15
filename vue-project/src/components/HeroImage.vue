<script>
    export default {
        data() {
            return {
                go: 'UnLock 15%'
            }
        }
    }
</script>
<template>
    <div class="container">
        <img
            src="../assets/Image/anete-lusina-zwsHjakE_iI-unsplash.jpg"
            alt="Snow"
            style="width: 100%"
        />
        <div>
            <button class="btn btn-primary">
                {{ go }}
            </button>
        </div>
    </div>
</template>
<style scoped>
    .container {
        position: relative;
        width: 100%;
    }

    .container img {
        width: 100%;
        height: auto;
    }

    .container .btn {
        position: absolute;
        bottom: 5%;
        left: 50%;
        transform: translate(-50%, -50%);
        -ms-transform: translate(-50%, -50%);

        color: white;
        font-size: 16px;
        padding: 12px 24px;
        border: none;
        cursor: pointer;
        border-radius: 5px;
        text-align: center;
    }

    .container .btn:hover {
        background-color: black;
    }
</style>
