<template>
  <div id="app">
    <h1>領収書</h1>
    <div style="margin: 15px">
      ○○スーパー○○店<br />TEL000-000-000 <br />20xx年04月01日 (月) 13:27
    </div>
    <table id="itemTable">
      <tr>
        <td>{{ name1 }}</td>
        <td>￥{{ price1 }}</td>
      </tr>
      <tr>
        <td>{{ name2 }}</td>
        <td>￥{{ price2 }}</td>
      </tr>
      <tr>
        <td>{{ name3 }}</td>
        <td>￥{{ price3 }}</td>
      </tr>
      <tr>
        <td>{{ name4 }}</td>
        <td>￥{{ price4 }}</td>
      </tr>
      <tr>
        <td colspan="2">--------------------------------------</td>
      </tr>
      <tr>
        <td>合計</td>
        <td>￥{{ price1 + price2 + price3 + price4 }}</td>
      </tr>
      <tr>
        <td>お預かり</td>
        <td>￥{{ deposit }}</td>
      </tr>
      <tr>
        <td>お釣り</td>
        <td>￥{{ deposit - (price1 + price2 + price3 + price4) }}</td>
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
      name1: "ネギ",
      price1: 190,
      name2: "ジャガイモ",
      price2: 208,
      name3: "トマト",
      price3: 435,
      name4: "ニンジン",
      price4: 372,
      deposit: 1300,
    };
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
