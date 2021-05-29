<template>
  <TodoList></TodoList>
</template>

<script>
import TodoList from "./components/TodoList.vue";
export default{
  name: 'app',
  components: {TodoList},
}
</script>

<style>

</style>
,
methods:{
toggleFinish(recycleItem){
this.items.map((item,index)=>{
if (item.id === recycleItem.id){
this.items.splice(index, 1);
}
})
}
}
@click="toggleFinish(item)"