<template>
    <v-layout row>
        <v-flex xs12 sm6 offset-sm3>
            <v-card>
                <v-toolbar color="cyan" dark>
                    <v-toolbar-side-icon></v-toolbar-side-icon>

                    <v-toolbar-title>To Do </v-toolbar-title>

                    <v-spacer></v-spacer>

                    <v-btn icon>
                        <v-icon>search</v-icon>
                    </v-btn>
                </v-toolbar>
                <v-list two-line >
                    <v-list-tile>Completed tasks: {{todos.filter(item => item.done === 1).length}}</v-list-tile>
                    <template v-for="todo in done">

                        <v-list-tile>
                            <v-list-tile-content>
                                <v-list-tile-title v-html="todo.title"></v-list-tile-title>
                                <v-list-tile-sub-title v-html="todo.project"></v-list-tile-sub-title>
                            </v-list-tile-content>
                        </v-list-tile>
                    </template>
                </v-list>
                <hr>
                <v-list two-line >
                    <v-list-tile>Pending tasks: {{todos.filter(item => item.done === 0).length}}</v-list-tile>
                    <template v-for="todo in undo">

                        <v-list-tile>
                            <v-list-tile-content>
                                <v-list-tile-title v-html="todo.title"></v-list-tile-title>
                                <v-list-tile-sub-title v-html="todo.project"></v-list-tile-sub-title>
                            </v-list-tile-content>
                        </v-list-tile>
                    </template>
                </v-list>
            </v-card>
        </v-flex>
    </v-layout>
</template>

<script>
export default {
    name: "ToDoList",
    props: ['todos'],
    computed:{
        done: function () {
            return this.todos.filter( item => {
                if(item.done === 1){
                    return item
                }
            })
        },
        undo: function () {
            return this.todos.filter( item => {
                if(item.done === 0){
                    return item
                }
            })
        }
    }
}
</script>

