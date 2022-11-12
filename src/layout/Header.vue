<template>
    <div class="header">
        <nav class="navbar navbar-expand-sm navbar-light bg-light">
            <div style="float:left; width: 65%;">
                <span class="box">
                    <b-icon-flower1></b-icon-flower1> FASHION COMMUNITY
                </span>
            </div>
            <div class="container-fluid" style="float:right; width:25%;padding-left:1px;border-left: 1px solid black; margin-right: 2px;">
                <ul class="navbar-nav">
                    <li class="nav-item">
                        <router-link to="/" class="nav-link">
                            <b-icon icon="house-door" font-scale="1"></b-icon>HOME
                        </router-link>
                    </li>
                    <li class="nav-item">
                        <div v-if="isLogin === 'true'">
                            <router-link to="/closet" class="nav-link">CLOSET </router-link>
                        </div>
                        <div v-else>
                            <router-link to="/login" class="nav-link">ClOSET </router-link>
                        </div>
                    </li>
                    <li class="nav-item">
                        <div v-if="isLogin === 'true'">
                            <!-- <button @click="logout">LOGOUT</button> -->
                            <b-button @click="logout" variant="light">LOGOUT</b-button>
                        </div>
                        <div v-else>
                            <router-link to="/login" class="nav-link">LOGIN </router-link>
                        </div>
                    </li>
                    <li class="nav-item">
                        <router-link to="/signUp" class="nav-link">SIGNUP</router-link>
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

.box {
    color: black;
    font-size: xx-large;
    font-weight: lighter;
    height: 100%;
    border-bottom: 2px solid black;
}
</style>

<script>
export default ({
    data() {
        return {
            userid: localStorage.getItem("userid"),
            isLogin: localStorage.getItem("isLogin")
        }
    },
    methods: {
        logout() {
            localStorage.removeItem('isLogin');
            localStorage.removeItem('userid');
            this.$router.go();
        }
    },
})
</script>
