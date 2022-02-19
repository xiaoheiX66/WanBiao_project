<template>
     <table class="table table-striped">
            <thead>
                <tr>
                    <th scope="col">
                        <input type="checkbox" v-model="checkAll">
                    </th>
                    <th scope="col">#</th>
                    <th scope="col">待办事项</th>
                    <th scope="col">是否完成</th>
                    <th scope="col">添加时间</th>
                    <th scope="col">操作</th>
                </tr>
            </thead>
            <tbody>
                <!-- 使用is让浏览器知道这个tr是跟这个组件有关系 -->
                <TodoItem is="todo-item" v-for="(item,index) in list" :item="item" :index="index" :select-ids="selectIds"
                    :select-item="selectItem" :key="item.id">   
                <th scope="row">
                <input type="checkbox" :checked="selectIds.includes(item.id)">
                 </th>  
                    </TodoItem>
            </tbody>
        </table>
</template>

<script>
import TodoItem from './TodoItem.vue'
export default {
     props: ['list'],
     data() {
         return {
             selectIds: []
         }
     },
     methods:{
    selectItem(id) {
        const idx = this.selectIds.indexOf(id)
        if (idx >= 0) {
            // 存在就删除
            this.selectIds.splice(idx, 1)
        } else {
            // 不存在添加
            this.selectIds.push(id);
        }
    }
            },
     computed: {
        checkAll: {
            get() {
                return this.list.every(item => this.selectIds.includes(item.id))
            },
            set(n) {
                if (n) {
                    this.selectIds = this.list.map(item => item.id);
                } else {
                    this.selectIds = []
                }
            }
        },
       
    },
    components:{
       TodoItem 
    }
}
</script>