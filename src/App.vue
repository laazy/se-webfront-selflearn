<template>
  <div id="app">
    <h1>your todolist</h1>
  <input id="input1" v-model="newInput"></input>
  <button id="button1" v-on:click="addNew()">addNew</button>
  <li v-for="item in todoList">
    <span @click="changeEditable(item)" v-show="!item.edit">{{ item.data }}</span>
    <span v-show="item.edit"><input type="text" :name="index" v-model="item.data"><span @click="changeEditable(item)">确定</span></span>
    <span class="remove" @click="remove(index)" style="color:red">X</span>
  </li>
    <!--router-view/-->
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      todoList: [{data: 'hav a try!', edit: false}],
      newInput: ''
    }
  },
  methods: {
    addNew () {
      var item = {
        data: this.newInput,
        edit: false
      }
      this.todoList.push(item)
      this.newInput = ''
    },
    remove (index) {
      this.todoList.splice(index, 1)
    },
    changeEditable (item) {
      item.edit = !item.edit
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
  margin:40px auto;
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
