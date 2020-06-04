<template>
    <section id="todos">
        <div class="todo" v-for="todo in todos" :key="todo.id"> 
            <div class="item">
                <h2>{{todo.title}}</h2>
                <p>{{todo.desc}}</p>
            </div>
            <button class="item_button" @click="todoDone()">✔️</button>
        </div>
    </section>
</template>

<script>
    export default {
        name:"Todos",
        props: ["todos"],
        methods:{
            todoDone(){
                this.$emit('todoDone')
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>