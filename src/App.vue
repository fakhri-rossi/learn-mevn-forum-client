
<template>
  <h1>Test 123</h1>
  <p>{{ dataMessage.message }}</p>
</template>

<script setup>
  import axios from 'axios';
  import { ref, onMounted } from 'vue';

  const dataMessage = ref(null);

  const getMessage = async () => {
    try {
      const { data } = await axios.get('http://localhost:3000/');
      dataMessage.value = data;
      console.log(dataMessage);
    } catch (error) {
      console.log(error);
    }
  } 

  onMounted(() => {
    getMessage();
  })
</script>

<style>

</style>
