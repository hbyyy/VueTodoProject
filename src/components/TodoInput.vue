<template>
    <div>
        <input type="text" v-model="newTodoItem" placeholder="할 일을 추가하세요" v-on:keyup.enter="addTodo">
        <span class="addContainer" v-on:click="addTodo">
            <i class="addBtn fas fa-plus" aria-hidden="true"></i>
        </span>
    </div>
</template>

<script>
export default {
    data() {
        return {
            newTodoItem: ''
        }
    },
    methods: {
        addTodo() {
            if (this.newTodoItem !== ''){
                var value = this.newTodoItem && this.newTodoItem.trim();
                localStorage.setItem(value, value);
                this.clearInput();
            }
        },
        clearInput() {
            this.newTodoItem = '';
        }
    }
}
</script>

<style>

</style>