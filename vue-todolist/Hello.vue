<template>
  <div id="APP">
      <h1>{{title}}</h1>
      <h2 v-html="subTitle"></h2>
      <input v-model = "newItem" v-on:keyup.enter="addNewItem" />
      <ul v-for="item in items">
        <li v-text="item.label" v-bind:class="{finished:item.isFinished}"
         v-on:click="toggerFinished(item)"></li>
      </ul>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      title: 'This is a TodoList',
      subTitle:'<small>winter.zhang</small>',
      items:[],
      newItem:''
    }
  },
  methods:{
    toggerFinished:function(item){
      item.isFinished = !item.isFinished;
    },
    addNewItem:function(){
      this.items.push({
        label:this.newItem,
        isFinished:false
      })
      this.newItem='';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
.finished{
  text-decoration:underline;
}
</style>
