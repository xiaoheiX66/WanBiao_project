<template>
    <button class="btn">
        <slot>按钮</slot>
    </button>
</template>

<script>
export default {
    name:"TodoButton",
    props:['text'],
    data(){
        return{
           
        }
    }
}
</script>