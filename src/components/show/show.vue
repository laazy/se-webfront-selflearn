<template>
    <div id="show">
        <h2>your todolist</h2>
        <ul>
            <li v-for="item in currentItems">{{ item.text }}</li>
        </ul>
    </div>
</template>

<script>
    export default{
      el: '#show',
      data: {
        currentItems: []
      },
      methods: {
        addNew: function (item) {
          this.currentItems.push(item)
        }
      }
    }
    // showItems.$on('addNew', function(item) {
    // this.currentItems.push(item)
// });
</script>