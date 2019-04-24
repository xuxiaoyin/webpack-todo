<template>
  <div :class="['todo-item', todo.completed ? 'completed' : '']">
    <input 
      type="checkbox"
      class="toggle"
      v-model="todo.completed"
    >
    <label>{{todo.content}}</label>
    <button class="destory" @click="deleteTodo"></button>
  </div>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    }
  },
  methods: {
    deleteTodo() {}
  },
}
</script>

<style lang="stylus" scoped>
.todo-item{
  position: relative;
  background: #fff;
  font-size: 24px;
  border-bottom: 1px solid rgba(0,0,0,0.06)
  &:hover{
    .destory:after{
      content: 'x'
    }
  }
  lable{
    white-space: pre-line;
    word-break: break-all;
    padding: 15px 60px 15px 15px;
    margin-left: 45px;
    display: block;
    line-height: 1.2;
  }
}
</style>

