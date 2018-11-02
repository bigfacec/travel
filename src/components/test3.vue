<template>
    <div class="app">
      <input type="text" v-model="inputValue">
      <button @click="handleAdd">提交</button>
      <todo-item v-for='(item,index) in todoList' :content="item" :index="index" :todoList="todoList"></todo-item>
      <p>----------------------------</p>
      <todo-item-two v-for='(item,index) in todoList' :content="item" :index="index" @delete="handleItemDelete"></todo-item-two>
    </div>
</template>
<script>
  var TodoItem = {
    //父组件向子组件传值
    props:['content','index','todoList'],
    template:"<li>{{content}} <span @click='deleteItem(index)'>-</span></li>",
    methods:{
      deleteItem(index){
        this.todoList.splice(index,1)
      }
    }
  }
  var TodoItemTwo = {
    //父组件向子组件传值
    props:['content','index'],
    template:"<li>{{content}} <span @click='handleItemClick'>-</span></li>",
    methods:{
      handleItemClick(){
        this.$emit('delete',this.index);
      }
    }
  }
  export default {
    name: "test3",
    data(){
      return{
        inputValue:'',
        todoList:['起床','吃早饭','学习','吃午饭','睡午觉']
      }
    },
    components:{
      TodoItem:TodoItem,
      TodoItemTwo:TodoItemTwo
    },
    methods:{
      handleAdd(){
        this.todoList.push(this.inputValue);
        this.inputValue = '';
      },
      handleItemDelete(index){
      // console.log(index);
        this.todoList.splice(index,1);
      }
    }
  }
</script>

<style lang="sass" scoped>
  //子组件的样式需要进行渗透
  li /deep/ span
    display: inline-block
    width: 15px
    height: 15px
    background-color: red
    color: #fff
    border-radius: 50%
    text-align: center
    font-weight: bold
    line-height: 12px
    vertical-align: top
    float: right
    margin-right: 90px
    cursor: pointer
</style>
