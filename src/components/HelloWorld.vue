<script setup>
import { ref } from 'vue'
import {sayHello} from "../api/hello";


const count = ref(0)
const message = ref("边走边爱的音乐台")

const hello = () => {
  sayHello().then(res => {
    message.value = res.data;
  });

};
</script>

<template>
  <h1>{{message}}</h1>
  <q-btn color="primary" @click="count++">点击次数{{count}}</q-btn>
  <br>
  <br>
  <q-btn color="primary" @click="hello">请求后端API</q-btn>



</template>

<style scoped>
a {
  color: #42b983;
}
.button-container {
  width: 50%;
  display: flex;
  flex-direction: row;

}

</style>
