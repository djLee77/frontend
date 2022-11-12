<template>
  <div class="hello">
    <div class="input_row">
      <label for="id">아이디</label>
      <input type="text" id="id" v-model="user.userid" />
    </div>
    <div class="input_row">
      <label for="password">비밀번호</label>
      <input type="password" id="password" v-model="user.password" />
    </div>
    <button v-on:click="login">로그인</button>
    <router-link to="/signUp">회원가입</router-link>
  </div>
</template>
  
<script>
//import { json } from 'body-parser';

export default {
  data: function () {
    return {
      user: {
        userid: "",
        password: "",
      }
    }
  },
  methods: {
    login: function (event) {
      this.$http
        .post("/api/users/login", {
          user: this.user,
        })
        .then(
          (res) => {
            //로그인 성공
            alert(res.data.message);
            var isLogin = null;
            var userid_s = res.data.userid
            
            if(res.data.message == 'Login successful'){
              isLogin = "true";
              localStorage.setItem("userid",userid_s)
            }
            localStorage.setItem("isLogin",isLogin);
            this.$router.push('/');
            this.$router.go();
          },
          (err) => {
            // error 를 보여줌
            alert("Login failed! please check your id or password");
          }
        )
        .catch((err) => {
          alert(err);
        });
        
    }
  }
};
</script>