<template>
  <div class="ToDoList">
    <h1 v-text="title"></h1>
    <ul>
      <li v-for="item in items" :key="item.id">
        <!--待办事项-->
        <span v-text="item.title"></span>
        <!--完成按钮-->
        <button>完成</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "TodoList",
  data(){
    return {
      title: "TodoList HMR",
      items:[
        {
          id: 1,
          title: '起床'
        },
        {
          id: 2,
          title: '睡觉'
        },
        {
          id: 3,
          title: '起床'
        },
        {
          id: 4,
          title: '睡觉'
        }
      ]
    }
  }
}
</script>

<style scoped>

</style>