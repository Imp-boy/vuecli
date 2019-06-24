<template>
  <div id="app">
    <router-view>
    </router-view>
  </div>
</template>

<script>
import Vue from "vue";
import VueRouter from "vue-router";
import login from "./components/login.vue";
import ElementUI from 'element-ui';
import 'element-ui/lib/theme-chalk/index.css';
import main from './components/main';

Vue.use(VueRouter);
Vue.use(ElementUI);

const routes = [
  {
    path: "/",
    redirect: '/login/admin/123456'
  },
  {
    path: "/login/:loginName/:password",
    component: login
  },
  {
    path: "/main/:user_id",
    component: main
  }
];

const router = new VueRouter({
  routes
});
export default {
  name: "app",
  router
};
</script>
<style>
  html,body{
    margin: 0;
    padding: 0;
    height: 100vh;
  }
</style>

