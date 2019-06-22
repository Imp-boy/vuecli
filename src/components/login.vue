<template>
  <div>
    <div>
      <label>用户名</label>
      <input v-model="loginName"/>
    </div>
    <div>
      <label>密码</label>
      <input />
    </div>
    <div>
      <label>用户名</label>
      <input />
    </div>
  </div>
</template>
<script>
export default {
    name:"login",
    props:{
        loginName:String
    }
}
</script>
