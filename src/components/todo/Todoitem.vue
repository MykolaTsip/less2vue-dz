<template>
<div ref="item">
    {{todoElement}}  <button @click="deleteTodo">REMOVE</button>
</div>
</template>

<script>
    export default {
        name: "Todoitem",

        props: {
            todoElement: {
                type: String
            }
        },

        methods: {
            deleteTodo() {
                this.$refs.item.style.display = 'none'
                console.log(this.$refs.item);
            }
        }
    }
</script>

<style scoped>
button {
    margin-left: 20px;
}

    div {
 line-height: 1.5;
    }
</style>
