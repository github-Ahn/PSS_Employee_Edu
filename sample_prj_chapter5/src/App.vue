<template>
  <div id="app">
    <div>
      <h1>input</h1>
      <input v-model="message" placeholder="edit me" />
      <p>Message is: {{ message }}</p>
    </div>
    <div>
      <h1>inputMultiline</h1>
      <span>Multiline message is:</span>
      <p style="white-space: pre-line">{{ multiline }}</p>
      <br />
      <textarea v-model="multiline" placeholder="add multiple lines"></textarea>
    </div>
    <div>
      <h1>CheckBox</h1>
      <input type="checkbox" id="checkbox" v-model="checked" />
      <label for="checkbox">{{ checked }}</label>
    </div>
    <div>
      <h1>CheckBoxMulti</h1>
      <input type="checkbox" id="jack" value="Jack" v-model="checkedNames" />
      <label for="jack">Jack</label>
      <input type="checkbox" id="john" value="John" v-model="checkedNames" />
      <label for="john">John</label>
      <input type="checkbox" id="mike" value="Mike" v-model="checkedNames" />
      <label for="mike">Mike</label>
      <br />
      <span>Checked names: {{ checkedNames }}</span>
    </div>
    <div>
      <h1>Radio</h1>
      <input type="radio" id="one" value="One" v-model="picked" />
      <label for="one">One</label>
      <br />
      <input type="radio" id="two" value="Two" v-model="picked" />
      <label for="two">Two</label>
      <br />
      <span>Picked: {{ picked }}</span>
    </div>
    <div>
      <h1>Select</h1>
      <select v-model="selected">
        <option disabled value="">Please select one</option>
        <option>A</option>
        <option>B</option>
        <option>C</option>
      </select>
      <br />
      <span>Selected: {{ selected }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      message: "",
      multiline: "",
      checked: false,
      checkedNames: [],
      picked: "",
      selected: "",
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
</style>
