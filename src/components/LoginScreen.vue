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
          Залогиньтесь, пж
        </header>
        <br>
        <input type="text" name="login" placeholder="почта">
        <br><br>
        <input type="password"  placeholder="пароль">
        <br><br>
        <input type="submit"  value="войти">
      </div>
      <div class="register" v-bind:class="{none:LoginTab}" id="registerField">
        <header>
          Зарегайтесь, пж
        </header>
        <input type="text" name="email" placeholder="почта">
        <br><br>
        <input type="password" name="password" placeholder="пароль" >
        <br><br>
        <input type="password" name="password" placeholder="повторите пароль">
        <br><br>
        <input type="submit" name="submit" value="зарегистрироваться">
      </div>
    </div>
  </body>
</template>


<script>
export default {
  data(){
  return{
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
