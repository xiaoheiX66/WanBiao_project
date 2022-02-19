<template>
     <div class="input-group mb-3">
            <input type="text" class="form-control" v-model="todo" ref="input" @keyup.enter="addItem">
            <button class="btn btn-success" type="button" @click="addItem">添加</button>
        </div>
</template>

<script>
export default {
    data(){
        return{
            todo:''
        }
    },
     methods: {
    addItem() {
        this.$emit('add', this.todo)
        this.todo = ''
        this.$refs.input.focus();
    }
            },
}
</script>