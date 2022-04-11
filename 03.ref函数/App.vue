<template>
  <!-- vue3可以没有根标签 -->
  <h1>APP组件</h1>
  <h2>name:{{ name }}</h2>
  <h2>age:{{ age }}</h2>
  <h3>type:{{ job.type }}</h3>
  <h3>type:{{ job.salary }}</h3>
  <button @click="changeInfo">修改</button>
</template>

<script>
import { ref } from "@vue/reactivity";
export default {
  name: "App",
  setup() {
    const name = ref("andy");
    const age = ref(18);
    const job = ref({
      type: "frontend",
      salary: "30K",
    });

    function changeInfo() {
      name.value = "red";
      age.value = 20;
      job.value.type = "backend";
      job.value.salary = "60K";
    }
    return {
      name,
      age,
      job,
      changeInfo,
    };
  },
};
</script>
