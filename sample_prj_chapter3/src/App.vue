<template>
  <div>
    <h1>ログイン</h1>
    <template v-if="loginType === true">
      <label class="itemLabel">username</label>
      <input
        class="itemInput"
        placeholder="名前を入力してください。"
        key="username-input"
      />
    </template>
    <template v-else>
      <label class="itemLabel">e-mail</label>
      <input
        class="itemInput"
        placeholder="メールアドレスを入力してください。"
        key="email-input"
      />
    </template>
    <button v-on:click="loginType = !loginType">切り替え</button>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      loginType: false,
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
  display: grid;
}

.itemLabel {
  margin: 10px;
}

.itemInput {
  width: 250px;
  height: 20px;
  margin: 10px;
}
</style>
