<template>
  <div class="ToDoList">
    <h1 v-text="title"></h1>
    <ul>
      <li v-for="item in items" :key="item.id">
        <!--待办事项-->
        <span v-text="item.title"></span>
        <!--完成按钮-->
        <button @click="toggleFinish(item)">完成</button>
      </li>
    </ul>
    <div><input type="text" v-model="newItem">
      <button @click="addNewItem">添加</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoList",
  data(){
    return {
      title: "TodoList HMR",
      items: [],
      id:0,
      newItem: '',
    }
  },
  methods:{
    toggleFinish(recycleItem){
      this.items.map((item,index)=>{
        if (item.id === recycleItem.id){
          this.items.splice(index, 1);
        }
      })
    },
    addNewItem(){
      this.items.push({
        id: this.id, //id唯一,自增
        title: this.newItem //todo title
      })
      this.id++; // ID自增
      this.newItem = ''; //清空input
    }
  }
}
</script>

<style scoped>

</style>