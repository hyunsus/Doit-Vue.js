<template>
  <section>
    <ul>
      <li v-for="(todoItem, index) in todoItems" :key="todoItem" class="shadow">
        <i class="checkBtn fas fa-check" aria-hidden="true"></i>
        {{ todoItem }}
        <span
          class="removeBtn"
          type="button"
          @click="removeTodo(todoItem, index)"
        >
          <i class="fa fa-trash-alt" aria-hidden="true"></i>
        </span>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {
      todoItems: [],
    };
  },
  created() {
    if (localStorage.length > 0) {
      for (var i = 0; i < localStorage.length; i++) {
        this.todoItems.push(localStorage.key(i));
      }
    }
  },
  methods: {
    removeTodo(todoItem, index) {
      localStorage.removeItem(todoItem);
      this.todoItems.splice(index, 1);
    },
  },
};
</script>

<style scoped>
ul {
  list-style-type: none; /* 목록 아이템의 스타일을 지정 */
  padding-left: 0px;
  margin-top: 0;
  text-align: left;
}
li {
  display: flex; /* 비율 기준의 레이아웃 방식인 flex로 지정 */
  min-height: 50px;
  height: 50px;
  line-height: 50px;
  margin: 0.5rem 0;
  padding: 0 0.9rem;
  background: white;
  border-radius: 5px;
}
.fixBtn {
  margin: auto;
  color: #4346de;
}
.checkBtn {
  line-height: 45px;
  color: #62acde;
  margin-right: 5px;
}
.removeBtn {
  margin-left: auto;
  color: #de4343;
}
.btnGroup {
  margin-left: auto;
}

/* 데이터가 나가고 들어오는 동작을 정의하는 CSS*/
.list-enter-active,
.list-leave-active {
  transition: all 1s;
}
.list-enter,
.list-leave-to {
  opacity: 0;
  transform: translateY(30px);
}
</style>
