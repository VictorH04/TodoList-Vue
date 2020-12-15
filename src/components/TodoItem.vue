<template>
    
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <p>
            
            <input type="checkbox" v-on:change="markComplete">
            
            {{todo.title}}

            <button @click="$emit('del-todo', todo.id)" class="del">&#x2715;</button>
        </p>
    </div>

</template>

<script>
export default {
    name: 'TodoItem',
    props: ['todo'],
    methods: {
        markComplete() {
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>

<style scoped>
    .todo-item {
        background: #f4f4f4;
        padding: 10px;
        border: 3px #ccc solid;
        margin: 20px 20px;
    }

    .is-complete {
        text-decoration: line-through;
    }

    .del {
        background: #f10000;
        color: #fff;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }

</style>