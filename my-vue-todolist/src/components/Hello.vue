<template>
  <div id="APP">
      <h1>{{title}}</h1>
      <h2 v-html="subTitle"></h2>
      <input v-model = "newItem" v-on:keyup.enter="addNewItem" />
      <ul v-for="(item,index) in items">
        <li v-text="item.label" v-bind:class="{finished:item.isFinished}"
         v-on:click="toggerFinished(item)"></li><span class='del' v-on:click="removeFinished(index)">X</span>
      </ul>
  </div>
</template>

<script>
import Store from '../store.js';
export default {
  name: 'hello',
  data () {
    return {
      title: 'This is a Vue TodoList',
      subTitle:'<small>winter.zhang</small>',
      items:Store.fetch(),
      newItem:''
    }
  },
  watch:{
    items:{
      handler:function(items){
        Store.save(items);
      },
      deep:true
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
    },
    removeFinished: function(index){
      this.items.splice(index,1)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
input{
  width: 300px;
  height: 20px;
  padding: 5px 0 5px 10px;
  outline: none;
  border: 2px solid #ccc;
  border-radius: 10px;
}
ul {
  padding: 5px 0; 
  color: #fff;
}

li {
  display: inline-block;
  width:245px;
  height: 20px;
  padding: 5px 0 5px 10px;
  border-radius: 5px;
  font-size: 20px;
  background-color: rgba(65,184,131,.69);
  text-align: left;        
}
span.del{
  display:inline-block;
  width:30px;
  height:20px;
  padding: 5px 0 5px 10px;
  line-height: 20px;
  margin-left: 20px;
  border-radius:10px;
  background-color: rgba(65,184,131,.80);
}

a {
  color: #42b983;
}
li.finished{
  text-decoration:line-through;
  color:#000;
}

</style>
