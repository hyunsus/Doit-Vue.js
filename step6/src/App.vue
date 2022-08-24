<template>
  <div id="app">
    <TodoHeader></TodoHeader>
    <TodoInput v-on:addTodo="addTodo"></TodoInput>
    <TodoList v-bind:propsdata="todoItems"></TodoList>
    <TodoFooter></TodoFooter>
  </div>
</template>

<script>
import TodoHeader from "./components/TodoHeader.vue";
import TodoInput from "./components/TodoInput.vue";
import TodoList from "./components/TodoList.vue";
import TodoFooter from "./components/TodoFooter.vue";

export default {
  components: {
    TodoHeader: TodoHeader,
    TodoInput: TodoInput,
    TodoList: TodoList,
    TodoFooter: TodoFooter,
  },
  data() {
    return {
      todoItems: [], // List에서 선언했던 데이터를 담을 todoItems 빈 배열로 선언
    };
  },
  methods: {
    addTodo(todoItem) {},
  },
};
</script>
<style>
/*
  text-align = 애플리케이션 전체에서 사용하는 텍스트의 정렬 방식을 선택
  background-color = 애플리케이션 전체의 배경 색을 꾸미기 위해 지정
  border-style = 할 일을 입력하는 인풋 박스의 테두리 모양을 정의
  box-shadow = 할 일을 입력하는 인풋 박스와 할 일 아이템의 아래 그림자 정의
  
*/
body {
  text-align: center;
  background-color: #f6f6f8;
}
input {
  border-style: groove;
  width: 200px;
}
button {
  border-style: groove;
}
.shadow {
  box-shadow: 5px 10px 10 px rgba(0, 0, 0, 0.03);
}
</style>
<style>
</style>
