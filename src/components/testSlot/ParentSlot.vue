<template v-slot="header">
   <div>
        <span>老父亲的插槽</span>
        <TemplateSlotss>
           
        </TemplateSlotss>
        
   </div>
</template>


<script>
import TemplateSlot from './templateSlot.vue'
import TemplateSlotss from './TemplateSlotss.vue'
export default {
    name:"ParentSlot",
    data(){
        return{}
    },
    components:{
        TemplateSlotss,
        TemplateSlot
    }
}
</script>