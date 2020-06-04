<template>  
<div>
    <h1>To do list</h1>
    
    <Todos @todoDone="deleteTodo(todos.s)" :todos = "todos"></Todos>
    <Header @addTodo="createTodo">

    </Header>
</div>
</template>

<script>
import Header from './components/header';
import Todos from './components/todos';


export default {
  
  name: 'App',
  components:{
    Header,
    Todos
  },
  data() {
    return {
      
      todos: [
      {   id :"1",
        title: 'todo smth',
        desc: 'deesc smth',
        
      },
      { id: "2",
        title: 'todo smth',
        desc: 'deesc smth',
       
      },
      { id: "3",
        title: 'todo smth',
        desc: 'deesc smth',
        
      }
    ],
    newTodo:{
      
      title:"",
      desc:""
    }
    }
  },
  methods:{
    deleteTodo(index){
      this.todos.splice(index,1);
    },
    createTodo(Title,Desc){
      let newTodo = {
          id: this.todos.length+2,
          title: Title,
          desc: Desc
          };
      this.todos.push(newTodo);
    }
    
  }
  
  
}
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
