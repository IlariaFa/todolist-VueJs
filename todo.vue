<template>
     
     <form v-on:submit.prevent="onSubmit">
     <label for="nexTodo">New Todo</label>
     <input type="text" name="nexTodo" id="newTodo" value="" v-model="newTodo" class="todo-input" placeholder="what needs to be done" @keyup.enter="addTodo">
    
     <div v-for="(todo, index) in todos":key="todo.id" class="todo-item" >{{todo.title}} <input type="checkbox" v-model="todo.completed" ><br>{{todo.prova}}</div>
     
    
     <div class="remove-item" @click="removeTodo(index)">
         &times;
     </div>
     <button type="submit" name="button" @click="addTodo">Add</button>
    </form>

</template>

<script>

export default{
  name: 'todo-list',
  data (){
    return{
      newTodo: '', // what we put in the v-model up in the template
      idForTodo: 3,
      todos: [
       {
         'id':1,
         'title':'Remember well',
         'prova': 'encore et encore',
         'completed':false,
       }, 
       {
        'id':2,
        'title':'pour se rapeller',
        'completed': false,
       },
      ]
    }
  },
  methods : {
    addTodo(){
    
      this.todos.push({ //you whant to push an object
        id: this.idForTodo,
        title: this.newTodo,
        completes: false,
      })
      this.newTodo=''
      this.idFortodos++
    },
  removeTodo(index){
this.todos.place(index,1)
  }
  }
}


</script>

<style>

.todo-input {
  width: 100%;
  padding: 10px 18px;
  font-size: 18px;
  margin-bottom: 16px;

}

.remove-item {
  cursor: pointer;
  margin-left: 14px;
 
}

.completed{
  text-decoration: line-through;
}
</style>
