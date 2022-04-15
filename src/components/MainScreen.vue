<template>
<body>

<br><br>
  <h2 class="header">
    Нынешние стоки:
  </h2>
  <div class="stonks" id = "app">
    <table width = "100%">
    <thead>
      <tr>
        <th width="60%">Имя стока</th>
        <th width="30%">Доходность</th>
        <th >цена</th>
      </tr>
    </thead>

    <tbody>

        <tr>
          <td>
            <b>{{stock}}</b>
            <p>{{ticker}}</p>
          </td>
          <td class="profitability positive">
            {{profit}}
            <p>{{prProfit}}</p>
          </td>
          <td>{{price}}</td>
        </tr>

    </tbody>
    </table>
  </div>
</body>
</template>

<script>
export default {
  name: 'MainScreen',
  data() {
  return{
    stock: 'Имя стока',
    ticker:'Код стока',
    profit:'+72$',
    prProfit:'+300%',
    price:'96$'
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
    border: 2px solid #ffffff;
    border-bottom: 0px;
    position: relative;
    font-size: 1.3em;
    color: #ffffff;

}
.tabs:hover {
  cursor: pointer;
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
   text-align: left
 }
 .positive {
   color: green
 }
 .negative {
   color: red
 }
</style>
