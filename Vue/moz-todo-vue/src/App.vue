<template>
    <div id="app">
        <h1>
            To-Do List
        </h1>
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
export default {
    name: "app",
    components:{
        ToDoItem
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
