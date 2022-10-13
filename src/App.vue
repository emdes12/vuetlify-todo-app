<script>
import { watchEffect } from "Vue";

// let todoInp = document.querySelector("#inpt");

// let todos = ref([
//   {
//     id: 0,
//     dos: "Answer your e-mails",
//     itsDone: false,
//   },
//   {
//     id: 1,
//     dos: "Send mom a gift",
//     itsDone: false,
//   },
//   {
//     id: 0,
//     dos: "Post on LinkedIn",
//     itsDone: false,
//   },
//   {
//     id: 0,
//     dos: "Create your next Vue App",
//     itsDone: false,
//   },
// ]);

// let addNewDos = () => {
//   console.log(todoInp);
//   // pushIn();
// };

export default {
  data() {
    return {
      todoInp: "",
      todos: [],
    };
  },
  
  methods: {
    pushIn() {
      console.log(this.todoInp);
      let todoLength = this.todos.length;
      console.log(todoLength);

      this.todos.push({
        id: todoLength,
        dos: this.todoInp,
        itsDone: false,
      });
    },

    altDone() {
      alert("Completed, Congrat");
    },
  },
};
</script>

<template>
  <div class="container">
    <header>
      <input class="inpt" v-model="todoInp" placeholder="Enter a task" />
      <button @click="pushIn()">+</button>
    </header>

    <ul>
      <li v-for="todo in todos" :key="todo.id">
        <input type="checkbox" v-on:click="altDone()" /> {{ todo.dos }}
      </li>
    </ul>
  </div>
</template>

<style scoped>
#app {
  all: none;
  background-color: rgb(219, 219, 219);
}
* {
  margin: 0;
  box-sizing: border-box;
  padding: 0;
}

/*  */

.container {
  width: 400px;
  background-color: #ffffff;
  font-size: 18px;
  font-family: "Open Sans";
  font-weight: 700;
}

header {
  position: relative;
}

.inpt {
  width: 100%;
  border: none;
  padding: 20px;
  background-color: rgb(32, 44, 39);
  font-size: 18px;
  font-family: "Open Sans";
  color: #fff;
  font-weight: 700;
  height: 50px;
}

button {
  border: none;
  cursor: pointer;
  width: 50px;
  height: 50px;
  background-color: rgb(4, 161, 101);
  display: grid;
  place-items: center;
  font-size: 25px;
  font-family: "Open Sans";
  font-weight: 700;
  position: absolute;
  top: 0;
  right: 0;
  color: #fff;
}

ul {
  list-style: none;
  color: #000;
}

li {
  font-size: 18px;
  font-family: "Open Sans";
  font-weight: 700;
  padding: 10px 20px;
  width: 100%;
  height: 50px;
}

li:not(:last-child) {
  border-bottom: 2px solid rgb(219, 219, 219);
}
</style>
