<template>
  <div class="center">
    <div class="loginBlock">
      <div class="loginInfo">
        <label>用户名</label>
        <input type="text" v-model="Ln" placeholder="请输入用户名">
      </div>
      <div class="loginInfo">
        <label>密&nbsp;&nbsp;&nbsp;码</label>
        <input type="password" v-model="Pw" placeholder="请输入密码">
      </div>
      <input type="button" @click="intoMain" value="登录">
    </div>
  </div>
</template>
<script>
let vueObject = null;
document.addEventListener("keypress",function(event){
  if(event.keyCode == 13){
    vueObject.intoMain();
  }
});
export default {
  name: "login",
  props: {
    loginName: String,
    password: String
  },
  created(){
    vueObject = this;
  },
  data:function(){
    return {
      Ln: this.$route.params.loginName ? this.$route.params.loginName : "",
      Pw: this.$route.params.password ? this.$route.params.loginName : ""
    }
  },
  methods:{
    intoMain(){
      this.$router.push({
        path:"/main/admin"
      });
    }
  }
};
</script>
<style>
.center {
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  margin-top: 160px;
}
.loginBlock {
  width: 400px;
  padding: 20px 0;
  border-radius: 5px;
  border: 1px #999 solid;
}
.loginInfo {
  margin-top: 40px;
}
.loginInfo input {
  border: 1px #999 solid;
  border-radius: 2px;
}
/* 登录按钮 */
input[type="button"] {
  margin-top: 40px;
  width: 80px;
  height: 24px;
  border-radius: 2px;
  border: 1px #999 solid;
}
label {
  display: inline-block;
  width: 80px;
}
</style>
