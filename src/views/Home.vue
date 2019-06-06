<template>
  <div class="home">
    <p>
      姓名：
      <input type="text" v-model="userInfo.name">
    </p>
    <p>
      年龄：
      <input type="text" v-model="userInfo.age">
    </p>
    <p>
      性别：
      <input type="text" v-model="userInfo.gender">
    </p>

    <hr>
    <p>
      品名：
      <input type="text" v-model="products.name">
    </p>
    <p>
      价格：
      <input type="text" v-model="products.price">
    </p>
    <button @click="resetData">重置 data</button>
  </div>
</template>

<script>
import { products } from "./data";

function intialState() {
  return {
    products: JSON.parse(JSON.stringify(products)),
    userInfo: {
      name: "",
      age: "",
      gender: ""
    }
  };
}

export default {
  inject: ["reload"],
  name: "home",

  data() {
    return intialState();
  },

  methods: {
    resetData() {
      this.reload();
    }
  }
};
</script>

