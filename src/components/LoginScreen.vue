<template>
  <head>
    <meta charset="utf-8">
  </head>
  <body>
    <div class="container">

      <table width = "100%">
        <tr>
          <td id = "rt" class = "tabs" v-bind:class="{activeTab:LoginTab}" @click="loginFun"> <p>Вход</p> </td>
          <td id = "lt" class="tabs" v-bind:class="{activeTab:RegisterTab}" @click="registerFun"><p>Регистрация</p></td>
          </tr>
      </table>

      <div class="login" v-bind:class="{none:RegisterTab}" id="loginField">
        <header>
        Введите свою почту и пароль
        </header>
        <br>
        <input type="text" v-model="Mail" name="login" placeholder="почта">
        <br><br>
        <input type="password" v-model="Pass"  placeholder="пароль">
        <br><br>
        <input type="submit" @click="SignUp"  value="войти">
      </div>
      <div class="register" v-bind:class="{none:LoginTab}" id="registerField">
        <header>
          Введите свою почту и пароль
          </header>
        <input type="text" v-model="Mail" name="email" placeholder="почта">
        <br><br>
        <input type="password" v-model="Pass" name="password" placeholder="пароль" >
        <br><br>
        <input type="password" name="password2" placeholder="повторите пароль">
        <br><br>
        <input type="submit" @click="Register" name="submit" value="зарегистрироваться">

      </div>
    </div>
  </body>
</template>


<script>
import axios from "axios";
export default {
  data(){
  return{
  token:'',
  Mail:'1212',
  Pass:'1212',
  RegisterTab:false,
  LoginTab:true
  }
  },
  name: 'LoginScreen',
  methods: {
     loginFun() {
     this.LoginTab = true;
     this.RegisterTab = false;
      },
    registerFun() {
      this.LoginTab = false;
      this.RegisterTab = true;
      },
      Register(){
      axios.post('http://25.82.186.249:1339/api/account/registration', {
    email: this.Mail,
    password: this.Pass
  })
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });
      },
      SignUp(){
      axios.post('http://25.82.186.249:1339/api/account/signup', {
    email: this.Mail,
    password: this.Pass
  })
  .then(function (response) {
    localStorage.setItem("token",response.data.token);
    console.log(localStorage.token);
  })
  .catch(function (error) {
    console.log(error);
  });
      }

     }
}
</script>

<style>
.container {
  background-color: lightblue;
  width: 300px;
  margin: auto;
  text-align: center;
}


.none {
  display: none;
}

.tabs {
            position: relative;
            border: 10px;
            width: 100%;
            background-color: rgba(11, 177, 224, 0.82);
            padding: 10px;
            text-align: center;
            vertical-align: middle;
            border: 1px solid #ffffff;
            border-bottom: 0px;
            position: relative;
            font-size: 1.3em;
            color: #ffffff;
        }
.tabs:hover{
  cursor: pointer;
}
.activeTab{
  background-color: blue;
}
</style>
