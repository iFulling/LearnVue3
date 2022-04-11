<template>
  <!-- vue3可以没有根标签 -->
  <h1>APP组件</h1>
  <h2 v-show="person.name">name:{{ person.name }}</h2>
  <h2>age:{{ person.age }}</h2>
  <h2 v-show="person.sex">性别:{{ person.sex }}</h2>
  <h3>type:{{ person.job.type }}</h3>
  <h3>type:{{ person.job.salary }}</h3>
  <button @click="changeInfo">修改</button>
  <button @click="addsex">添加sex</button>
  <button @click="delname">删除name</button>
</template>

<script>
import { reactive } from "@vue/reactivity";
export default {
  name: "App",
  setup() {
    const person = reactive({
      name: "andy",
      age: 18,
      job: {
        type: "frontend",
        salary: "30K",
      },
    });
    function changeInfo() {
      person.name = "red";
      person.age = 20;
      person.job.type = "backend";
      person.job.salary = "60K";
    }
    function addsex() {
      person.sex = "男";
    }
    function delname() {
      delete person.name;
    }
    return {
      person,
      changeInfo,
      addsex,
      delname,
    };
  },
};
</script>
