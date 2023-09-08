<script setup>
    import Header from '@/_components/header.vue';
    import AddForm from '@/_components/addForm.vue';
    import TodoList from '@/_components/todoList.vue';
    import { ref } from 'vue';

    let todoList = ref([]);

    function addTodoItem(str){
        todoList.value.push({
            text: str,
            checked: false
        });
    }

    function deleteTodoItem(index){
        todoList.value.splice(index, 1);
    }

    function checkTodoItem(index){
        todoList.value[index].checked = !todoList.value[index].checked;
    }
    
</script>

<template>
    <div class="flex flex-col min-h-screen py-8 antialiased bg-slate-50">
        <main class="container mx-auto">
            <Header></Header>
            <AddForm @add-text="addTodoItem"></AddForm>
            <TodoList :list='todoList' @delete-item="deleteTodoItem" @check-item="checkTodoItem"></TodoList>
        </main>
    </div>
</template>

<style scoped></style>
