<template>
    <div class="inputBox Shadow">
        <input type="text" v-model="newTodoItem" placeholder="야 너두 할 수 있어 - !"
         v-on:keyup.enter="addTodo">
        <span class="addContainer" v-on:click="addTodo">
            <i class="addBtn fas fa-plus" aria-hidden="true"></i>
        </span>
        <modal class="cursorControll" v-if="showModal" @close="showModal=false">
            <h3 slot="header">에 라(Error)</h3>
            <span slot="footer" @click="showModal =false"> 일없슈? </span>
            <i class="classModalBtn fas fa-times" aria-hidden="true"></i>
        </modal>
    </div>
</template>
<script>
import Modal from './common/Modal.vue';
export default {
    components : {Modal},
    data() {
        return {
            newTodoItem: '',
            showModal: false
        }
    },
    methods: {
        addTodo() {
            if(this.newTodoItem !== ""){
                var value= this.newTodoItem && this.newTodoItem.trim();
                this.$emit('addTodo', value);
                this.clearInput();
            } else {
                this.showModal =! this.showModal;
            }
        },
        clearInput () {
            this.newTodoItem = '';
        }
    }
}
</script>
<style>
    input:focus {
        outline: none;
    }
    .inputBox {
        background: white;
        height: 50px;
        line-height: 50px;
        border-radius: 5px;
    }
    .inputBox input {
        border-style: none;
        font-size: 0.9rem;
    }
    .addContainer{
        float: right;
        background: linear-gradient(to right, #6478fB, #8763fb);
        display: block;
        width: 3rem;
        border-radius: 0 5px 5px 0;
        cursor: progress;
    }
    .addBtn{
        color: white;
        vertical-align: middle;
    }
    .cursorControll{
        cursor: progress ;
    }
</style>
