<template>
  <!-- vue3可以没有根标签 -->
  <h1>APP组件</h1>
  <h2>name:{{name}}</h2>
  <h2>age:{{age}}</h2>
  <button @click="sayHello">say</button>
</template>

<script>
export default {
  name: "App",
  setup() {
    let name = "andy";
    let age = 18;
    function sayHello() {
      alert(`我是${name},我${age}岁`);
    }
    return {
      name,
      age,
      sayHello
    }
  },
};
</script>
