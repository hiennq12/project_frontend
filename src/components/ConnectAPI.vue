<script>
import {ref} from 'vue';

export default {
  name: 'ConnectAPI',
  async setup() {
    let user = ref(null);
    const data = await fetch('http://localhost:8000/user/1')
    if (!data.ok) {
      throw new Error('Network error: ', date.statusText)
    }
    user = await data.json()
    console.log('data');

    return {
      user
    }
  }
}

</script>

<template>
  <h1>TEST CONNECT API</h1>
  <div class="card text-center m-3">
    <h5 class="card-header">Simple GET Request</h5>
    <div class="card-body">User Email: {{ user?.email }}</div>
    <div class="card-body">User name: {{ user?.name }}</div>
  </div>
</template>

<style scoped>

</style>
