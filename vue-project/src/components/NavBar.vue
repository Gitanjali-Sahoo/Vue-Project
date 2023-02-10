<script setup>
    import { RouterLink, RouterView } from 'vue-router'
    // import Form from '../components/Form.vue'
</script>
<template>
    <nav class="navbar navbar-expand-lg bg-body-tertiary">
        <div class="container-fluid">
            <RouterLink class="navbar-brand" to="/">Digilib</RouterLink>
            <button
                class="navbar-toggler"
                type="button"
                data-bs-toggle="collapse"
                data-bs-target="#navbarSupportedContent"
                aria-controls="navbarSupportedContent"
                aria-expanded="false"
                aria-label="Toggle navigation"
            >
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                    <li class="nav-item">
                        <RouterLink
                            class="nav-link active"
                            aria-current="page"
                            to="/"
                            >Home</RouterLink
                        >
                    </li>
                    <!-- <li class="nav-item">
                        <RouterLink class="nav-link" to="/about"
                            >About</RouterLink
                        >
                    </li> -->
                    <li class="nav-item dropdown">
                        <a
                            class="nav-link dropdown-toggle"
                            href="#"
                            role="button"
                            data-bs-toggle="dropdown"
                            aria-expanded="false"
                        >
                            Browse
                        </a>
                        <ul class="dropdown-menu">
                            <li>
                                <a class="dropdown-item" href="#">Trending</a>
                            </li>
                            <li>
                                <a class="dropdown-item" href="#"
                                    >Collections</a
                                >
                            </li>
                            <li>
                                <a class="dropdown-item" href="#">Subjects</a>
                            </li>
                            <li><hr class="dropdown-divider" /></li>
                            <li>
                                <a class="dropdown-item" href="#">Login</a>
                            </li>
                        </ul>
                    </li>
                </ul>
                <div class="d-flex">
                    <router-link to="/about" custom v-slot="{ navigate }">
                        <button
                            class="btn btn-outline-success"
                            @click="navigate"
                            role="link"
                        >
                            Log In
                        </button>
                    </router-link>

                    <button class="btn btn-outline-success">Sign Up</button>
                </div>
            </div>
        </div>
    </nav>
    <RouterView />
</template>
<style scoped>
    .btn {
        margin: 10px;
    }
</style>
