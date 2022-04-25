<template>
  <div id="app">
    <h1>領収書</h1>
    <div style="margin: 15px">
      ○○スーパー○○店<br />TEL000-000-000 <br />20xx年04月01日 (月) 13:27
    </div>
    <table id="itemTable">
      <tr v-for="(item, index) in shoppingList" :key="index">
        <td>{{ item.name }}</td>
        <td>￥{{ item.price }}</td>
      </tr>
      <tr>
        <td colspan="2">--------------------------------------</td>
      </tr>
      <tr>
        <td>合計</td>
        <td>
          ￥{{
            shoppingList[0].price +
            shoppingList[1].price +
            shoppingList[2].price +
            shoppingList[3].price
          }}
        </td>
        <!-- <td>￥{{ getTotal() }}</td> -->
      </tr>
      <tr>
        <td>お預かり</td>
        <td>￥{{ deposit }}</td>
      </tr>
      <tr>
        <td>お釣り</td>
        <td>
          ￥{{
            deposit -
            shoppingList[0].price -
            shoppingList[1].price -
            shoppingList[2].price -
            shoppingList[3].price
          }}
        </td>
        <!-- <td>￥{{ getChange() }}</td> -->
        <!-- <td>￥{{ deposit - getTotal() }}</td> -->
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      shoppingList: [
        {
          name: "ネギ",
          price: 190,
        },
        {
          name: "ジャガイモ",
          price: 208,
        },
        {
          name: "トマト",
          price: 435,
        },
        {
          name: "ニンジン",
          price: 372,
        },
      ],
      deposit: 1300,
    };
  },
  methods: {
    //合算を算出する
    getTotal() {
      var total = 0;
      //ショッピングリスト(shoppingList)から価格(price)を取り出して足す
      //dataに定義したオブジェクトにアクセスするためには「this.」を付けます
      for (var idx in this.shoppingList) {
        total = total + this.shoppingList[idx].price;
        //配列[インデックス]→リストから該当インデックスに紐づくアイテムを取り出す
        //オブジェクト.プロパティ→オブジェクトのプロパティにアクセス
      }
      return total;
    },
    //釣り銭を計算する
    getChange() {
      //methodに定義したファクションにアクセスするためには「this.」を付けます
      return this.deposit - this.getTotal();
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#itemTable {
  display: inline-table;
}
tr > td {
  width: 120px;
  height: 30px;
}
</style>
