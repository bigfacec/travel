<template>
    <div class="test2">
        <input type="text" v-model="inputValue">
        <button @click="addItem">提交</button>
        <ol>
            <li v-for="(item,index) in list">{{item}}<span @click="deleteItem(index)">-</span></li>
        </ol>
    </div>
</template>
<script>
export default {
  name: "test2",
  data () {
    return {
      list:['起床','吃早饭'],
      inputValue:''
    };
  },
  methods:{
    addItem(){
      var liData = this.inputValue;
      this.list.push(liData);
      this.inputValue = '';
    },
    deleteItem(index){
      this.list.splice(index,1)
    }
  }
}
</script>
<style lang="sass" scoped>
  .test2
    width: 300px
    margin: 0 auto
    li span
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
