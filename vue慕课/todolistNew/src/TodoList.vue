<template>
  <div>
    <div>
      <input class="item" v-model="inputValue"/>
      <button @click="handleSubmit">提交</button>
    </div>
    <ul>
      <TodoItem v-for="(item,index) of list" :key="index" :content="item" :index="index" @delete="deleteItem"></TodoItem>
    </ul>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem'

export default {
  name: 'App',
  components: {  //获取组件    注册组件
    TodoItem
  },
  computed:{  //计算属性

  },
  data (){
    return {
      inputValue:'',
      list:[]
    }
  },
  methods:{
    handleSubmit(){
      //alert(123);
      //this是this.$data.list的缩写或别名
      this.list.push(this.inputValue);
      this.inputValue='';
    },
    deleteItem(index){
      this.list.splice(index,1);
    }
  }
}
</script>

<style scoped>
  /* scoped 样式可以向下渲染，不可以向上渲染 */
.item{
  background: lavender
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
