<template>
 <div class="content">
   <h2>{{todoCount}} Aufgaben für heute</h2>
   <h2>{{totalTime}} minuten</h2>
 <ul>
   <li v-for="todo in todos">{{todo.name}} {{todo.time}}min</li>
 </ul>

 <input v-model="newTodo"/>
 <input type="number" v-model="newTime">
 <button v-on:click="addTodo()">Eintrag hinzufügen</button>
 </div>
</template>

<script>
export default{
  name: 'App',
  data: function(){
    return{
      todos: [
        {
          name: 'Milch Kaufen',
          time:10
        },
        {
          name: 'yes',
          time:20
        }
        
      ],
      newTodo:'',
    }
  },
  methods:{
    addTodo: function(){
      if(this.newTodo!='')
      {
      this.todos.push({
        name: this.newTodo,
        time: parseInt(this.newTime),
      });
      this.newTodo='';
      this.newTime=0;
      }
    }
  },
  computed:{
    todoCount: function(){
      return this.todos.length;
    },
    totalTime: function(){
      var time=0;
      
      this.todos.forEach(function(todo){
        time+= todo.time;
      })
      return time;
    }
  }
  
}
</script>

<style>
.content{
  width: 800px;
  margin: 0 auto;
}
</style>
