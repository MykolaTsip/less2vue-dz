<template>
    <div id="app">
        <h1>
            Homework № 2
        </h1>
        <TodoAdd @todoEmit="addTodo"/>
        <hr>
        <TodoList :todoE="todoE"/>
    </div>
</template>

<script>
    import TodoList from "./components/todo/TodoList";
    import TodoAdd from "./components/todo/TodoAdd";

    export default {
        name: 'App',
        components: {
            TodoAdd,
            TodoList
        },

        data() {
            return {
                todoE: ''
            }
        },

        methods: {
            // todoEmit(event) {
            //     this.todoE = event
            //     // console.log(this.todoE)
            // }

            addTodo(event) {
                this.todoE = event
                // console.log(this.todoE)
            }
        },
    }
</script>

<style scoped>
    h1 {
        text-align: center;
    }
</style>
