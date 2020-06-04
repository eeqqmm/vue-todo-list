<template>
   <header>
       <div class="item">
            <input class="item__input" type="text" name="todoInput" id="todoInput"  v-model="todoTitle" :placeholder="inputPlace">
            <textarea class="item__textarea" name="todoDesc" id="todoDesc" v-model="todoDesc" cols="30"  rows="10" :placeholder="textareaPlace" ></textarea>
       </div>
       <button class="add-todo" id="createTodo" @click ="addTodo()">+</button>
   </header>

    
</template>

<script>
    export default {
        name: "Header",
        data() {
            return {
               todoTitle:"",
                todoDesc:"",
                inputPlace: "What to do ?",
                textareaPlace:"Description" 
            
            }
        },
        props:["todos"],
        methods:{
             addTodo(){
                    if (this.todoTitle != ""){
                          this.$emit('addTodo',this.todoTitle,this.todoDesc)
                    
                  
                         this.todoTitle = "",
                            this.todoDesc = ""
            }
        } 
        }
    }
  
</script>

<style>
   
</style>