<template>
<div class="head" >
      <header @click="GoToMain"  class="tabr">Главная страница</header>
      <header @click="GoToCabinet"  class="tabr">Мой кабинет</header>
      <header @click="GoToLogin"  class="tabr">Выйти</header>
</div>
      <component :is="page"></component>
</template>

<script>
import LoginScreen from './components/LoginScreen.vue'
import MainScreen from './components/MainScreen.vue'
import PersonalCabinet from './components/PersonalCabinet.vue'
export default {
  name: 'App',
  components: {
    LoginScreen,
    MainScreen,
    PersonalCabinet
  },
  data(){
  return{
  page:"PersonalCabinet"
  }
  },
  methods: {
  GoToMain(){
  this.page = "MainScreen"
  },
  GoToCabinet(){
  this.page = "PersonalCabinet"
  },
  GoToLogin(){
  this.page = "LoginScreen"
  }
  }
}

</script>

<style>
.tabr {
    display: table-cell;
    width: 25%;
    background-color: rgba(11, 177, 224, 0.82);
    padding: 10px;
    text-align: center;
    vertical-align: middle;
    border: 2px solid #ffffff;
    border-bottom: 0px;
    position: relative;
    font-size: 1.3em;
    color: #ffffff;
    font-family: Arial;
}
.none {
display: none;
}


</style>
