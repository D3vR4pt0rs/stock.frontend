<template>
<body>
  <div>

    <p class = "purse"><b>email:</b> example@mail.ru</p>
    <p class = "purse"><b>Мои деньги:</b> {{balance}}$</p>
    <h2 class="header">
      Мои стоки:
    </h2>
    <div class="stonks">
      <table width = "100%">
        <thead>
          <tr>
            <th width="30%">Имя стока</th>
            <th width="10%">Объём</th>
            <th width="20%">Доходность</th>
            <th >цена</th>
            <th>общая стоимость</th>
          </tr>
        </thead>

        <tbody>

          <tr>
            <td>
              <b>Имя стока</b>
              <p>код стока</p>
            </td>
            <td>2</td>
            <td class="profitability positive">
              +0$
              <p>+0%</p>
            </td>
            <td>96$</td>
            <td>192$</td>
          </tr>

        </tbody>
      </table>
    </div>
  </div>
  <div class="pop-up none" >
    <div class="pop-up-content">
      Сколько вы хотите положить денег?
      <br><br>
      <input type="number">
      <br><br>
      <input type="submit" name="" value="положить на счёт">
    </div>
  </div>
</body>
</template>

<style scoped>
.tabs {
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
.tabs:hover {
  cursor: pointer;
}

.purse {
  font-size: 18px;
  font-family: Arial;
}

 .header {
   font-family: Arial
 }



 thead {
   background-color: lightblue
 }

 tbody {
     background-color: #e4f0f5;
 }

 caption {
     padding: 10px;
     caption-side: bottom;
 }

 table {
     border-collapse: collapse;
     border: 2px solid rgb(200, 200, 200);
     letter-spacing: 1px;
     font-family: sans-serif;
     font-size: .8rem;
 }

 td,
 th {
     border: 1px solid rgb(190, 190, 190);
     padding: 5px 10px;
 }

 td {
     text-align: center;
 }

 .name {
   text-align: left;
 }
 .positive {
   color: green;
 }
 .negative {
   color: red;
 }

 .pop-up{
     width:100%;
     height: 2000px;
     background-color: rgba(0,0,0,0.5);
     position:fixed;
     top:0px;
 }
 .pop-up-content {
   background-color: white;
   text-align: center;
   width: 300px;
   height:auto;
   margin: auto;
   margin-top: 200px;
 }

</style>
<script>
import axios from "axios"
export default{
name: "PersonalCabinet",
data(){
return{
balance:0,
}
},
methods:{
GetMoney(){
axios.defaults.headers.common["Authorization"] =
               "Bearer " + localStorage.getItem("jwt");

axios.get('http://25.82.186.249:1337/api/account/balance', {}
)
  .then(response=>(this.balance = response.data.balance));


},
},
created: function(){
console.log(localStorage.getItem("token"));
this.GetMoney();
}
}
</script>
