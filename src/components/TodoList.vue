<template>
    <div>
        <div>
            <input v-model="work"/>
            <button @click="handleSubmit">提交</button>
        </div>
        <ul>
          <todo-item v-for="(item,index) of list" 
            :key="index"
            :content="item"
            :index="index"
            @delete="handleDelete"
            >
            {{item}}
            </todo-item>
        </ul>
    </div>
</template>

<script>
import TodoItem from './TodoItem'
// 以前用new Vue的時候是對象，在這裡是對象中的組件
export default {
    components: {
        TodoItem
    },
    // data: function() {  // ES5的語法
    data () {              // ES6的語法
        return {
            work: '',
            list: []
        }
    },
    methods: {
        handleSubmit () {
            this.list.push(this.work)
            this.work = ''
        },
        handleDelete (index) {
            this.list.splice(index, 1)
        }
    }
}
</script>

<style lang="">
    
</style>