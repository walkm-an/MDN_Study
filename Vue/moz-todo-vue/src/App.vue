<template>
    <div id="app">
        <h1>
            To-Do List
        </h1>
        
        <to-do-form v-on:todo-added="addToDo"> </to-do-form>

        <ul>
            <li v-for="item in ToDoItems" v-bind:key="item.id">
                <to-do-item :label="item.label" :done="item.done" :id="item.id"></to-do-item>
            </li>
        </ul>
    </div>
</template>

<script>
import ToDoItem from './components/ToDoItem.vue';
import uniqueID from 'lodash.uniqueid';
import ToDoForm from './components/ToDoForm.vue';
export default {
    name: "app",
    components:{
        ToDoItem,
        ToDoForm
    },
    data() {
        return {
            ToDoItems : [
                {id:uniqueID('todo-'), label: 'learn vue', done: false},
                {id:uniqueID('todo-'), label: 'create vue', done: true},
                {id:uniqueID('todo-'), label: 'have vue', done: true},
                {id:uniqueID('todo-'), label: 'learn blablabla', done: false}
            ]
        };
    },
    methods:{
        addToDo(toDoLabel) {
            this.ToDoItems.push({id:uniqueID('todo-'), label: toDoLabel, done: false})
        }
    }
};
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
