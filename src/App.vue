<template>
  <div id="app">
  <input id="input1" v-model="newInput"></input>
  <button id="button1" v-on:click="addNew()">addNew</button>
  <p v-for="item in todoList">{{item}}</p>
    <!--router-view/-->
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      todoList: ['111', '222'],
      newInput: ''
    }
  },
  methods: {
    addNew () {
      this.todoList.push(this.newInput)
      this.newInput = ''
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;}
#button1 {
  background-color: #4CAF50; 
  border: none;
  color: white;
  padding: 10px 10px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
}
#input1{
  width:360px;
  margin:20px auto;
}
#input1[type="text"],#btn1,#btn2{
  box-sizing: border-box;
  text-align:center;
  font-size:1.4em;
  height:2.7em;
  border-radius:4px;
  border:1px solid #c8cccf;
  color:#6a6f77;
  -web-kit-appearance:none;
  -moz-appearance: none;
  display:block;
  outline:0;
  padding:0 1em;
  text-decoration:none;
  width:100%;
}
#input1[type="text"]:focus{
  border:1px solid #ff7496;
}
</style>
