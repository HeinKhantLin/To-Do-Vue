<template>
  <ToDoList v-bind:todos="todos"/>
</template>

<script>
import ToDoList from './components/ToDoList'

export default {
  name: 'App',
  components: {
      ToDoList
  },
    data() {
        return {
            todos: [{
                title: 'Todo A',
                project: 'Project A',
                done: 0,
            }, {
                title: 'Todo B',
                project: 'Project B',
                done: 1,
            }, {
                title: 'Todo C',
                project: 'Project C',
                done: 0,
            }, {
                title: 'Todo D',
                project: 'Project D',
                done: 0,
            }],
        };
    },

}
</script>
