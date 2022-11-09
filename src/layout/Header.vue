<template>
    <div class="header">
        <nav class="navbar navbar-expand-sm navbar-light bg-light">
            <div class="container-fluid">
                <ul class="navbar-nav">
                    <li class="nav-item">
                        <router-link to="/" class="nav-link">Home</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link to="/login" class="nav-link">Login</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link to="/signUp" class="nav-link">SignUP</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link to="/closet" class="nav-link">Closet</router-link>
                    </li>
                </ul>
            </div>
        </nav>
    </div>
</template>

<style scoped>
.container-fluid {
    justify-content: flex-end;
}
</style>