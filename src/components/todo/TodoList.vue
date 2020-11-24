<template>
    <div>
        <ul>
            <li v-for="(todo, i) in todos" :key="`${todo}${i}`">
                <p>
                    <Todoitem :todoElement="todo"/>
                </p>
            </li>
        </ul>
    </div>
</template>

<script>
    import Todoitem from "./Todoitem";
    import {eventBus} from "../../main";

    export default {
        name: "TodoList",

        props: {
            todoE: {
                type: String,
            }
        },

        components: {
            Todoitem
        },

        data() {
            return {
                todos:
                    [
                        'Todolist Розбиваємо todolist на компоненти',
                        'Має бути компонент Todolist який має в собі масив тудушок',
                        'Компонент TodoItem в якому відображається наша тудушка і кнопка remove при кліці на котру ми будемо видаляти її',
                        'Компонент з інпутом та кнопкою яка добавляє нашу тудушку.'
                    ]
            }
        },



        created() {
            eventBus.$on('newTodo', (ev) => {
                    this.todos.push(ev)

            })

        },


    }
</script>

<style scoped>

</style>
