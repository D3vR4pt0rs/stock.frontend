<template>
<body>
  <div class="containeer">


  <div class="head" >
  <header id="personal-cabinet" onclick="mainPageFun()" class="tabs">Назад</header>
  </div>

  <h2 class="header">
    {{StockName}}
  </h2>
  <h4>{{Ticker}}</h4>
  <h1>{{Price}}</h1>
  <p>У меня: {{MyAmount}}</p>
  <input type="number" placeholder="количество">
  <input type="submit" name="" value="купить">
  <input type="submit" name="" value="продать">
  </div>
</body>
</template>

<script>
export default{
name:"CurrentStock",
data() {
return{
StockName:"Название стока",
MyAmount:"0",
Ticker:"код стока",
Price:"96$"
}
}
}
</script>
<style scoped>
.tabs {
    display: table-cell;
    width: 25%;
    background-color: rgba(11, 177, 224, 0.82);
    padding: 10px;
    clear: both;
    text-align: center;
    vertical-align: middle;
    border: 2px solid #ffffff;
    border-bottom: 0px;
    position: relative;
    font-size: 1.3em;
    color: #ffffff;

}

.containeer {
  font-family: Arial;
}


 .positive {
   color: green
 }
 .negative {
   color: red
 }
</style>
