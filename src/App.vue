<template>
  {{ user.first_name }} {{ user.last_name }}
  <br />
  {{ fullName }}
  <button @click="user.first_name = 'Bruno'">Atualizar</button>
</template>

<script>
import { ref, computed, watch } from 'vue';

export default {
  setup() {
    const user = ref({
      first_name: 'Jorge',
      last_name: 'Almeida'
    });
  
    const fullName = computed(() => `${user.value.first_name} ${user.value.last_name}`);

    watch(() => user.value.first_name, () => {
      console.log('Primeiro nome foi alterado');
    })

    return {
      user,
      fullName,
    };
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
