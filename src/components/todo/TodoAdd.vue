<template>
    <div>
        <div class="inp">
        <input
                type="text"
                placeholder="add new todo with EVENT_BUS"
                v-model="valueEventBus"
        >
        <button @click="addTodo">ADD NEW TOdo</button>
        </div>

<!--            <div class="inp">-->
<!--        <input-->
<!--                type="text"-->
<!--                placeholder="add new todo with EMITER"-->
<!--                v-model="valueEmiter"-->
<!--        >-->
<!--        <button @click="addTodoEmiter">ADD new todo with emiter</button>-->
<!--            </div>-->
    </div>
</template>


<script>
    import {eventBus} from "../../main";

    export default {
        name: "TodoAdd",

        data() {
            return {
                valueEventBus: '',
                valueEmiter: ''
            }
        },

        methods: {
            addTodo() {
                if (this.valueEventBus !== '') {
                    eventBus.$emit('newTodo', this.valueEventBus)
                    console.log(this.valueEventBus)
                }
            },

            addTodoEmiter() {
                this.$emit('todoEmit', this.valueEmiter)
            }
        }
    }
</script>

<style scoped>
    .inp {
        display: flex;
        justify-content: center;
        margin: 30px 0;
    }
</style>
