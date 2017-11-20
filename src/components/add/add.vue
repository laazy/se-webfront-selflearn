<template>
    <div id="add">
        <input type="text" name="newInput" v-model="newthing">
        <button v-on:clivk="addNew">新增</button>
    </div>
</template>

<script>
    export default{
      el: '#add',
      data: {
        todoItem: [],
        newItem: ''
      },
      methods: {
        addNew: function () {
          this.todoItem.push(this.newItem)
          // showItems.$emit('addNew', this.newItem)
        }
      }
    }
</script>
