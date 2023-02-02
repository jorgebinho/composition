<template>
  <img alt="Vue logo" src="./assets/logo.png" @click="changeName()">
  {{ name }}
  <hr>
  {{ user.first_name }} {{ user.last_name }}
  <br>
  {{ admin.first_name }} {{ admin.last_name }}
  <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import { ref, reactive } from 'vue';

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  setup() {
    const user = reactive({
      first_name: 'Jorge',
      last_name: 'Almeida'
    });

    const admin = ref({
      first_name: 'Admin',
      last_name: 'Master'
    });

    let name = 'Bruno';

    const changeName = () => {
      name = 'Bruno dos Santos';
      user.first_name = 'Claudio';
      admin.value.last_name = 'XXX';
    };

    return {
      name,
      changeName,
      user,
      admin
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
