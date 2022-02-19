<template>
     <div>总共：{{list2.length}}、已完成：{{completeAll.length}}、未完成{{uncompleteAll.length}}</div>
</template>

<script>
export default {
    props: ['list2'],
    computed: {
     completeAll() {
         return this.list2.filter(item => item.done)
     },
     uncompleteAll() {
         return this.list2.filter(item => !item.done)
     }
            },
}
</script>