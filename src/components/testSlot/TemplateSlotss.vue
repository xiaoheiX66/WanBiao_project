<template>
    <div>
        <slot name="header">子组件插槽</slot>
    </div>
</template>

<script>
export default {
    name:"TemplateSlot",
    data(){
        return{

        }
    }
}
</script>