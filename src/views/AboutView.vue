<script setup>
  import { reactive } from 'vue';
  import axios from 'axios';

  let form = reactive({
    email: '',
    password: '',
  });

  const login = async()=>{
    await axios.post('http://localhost:8000/api/login', form)
    .then(res=>{
      console.log(res);
    })
  }
</script>

<template>
  <div class="about">
    <form @submit.prevent="login">
      <input type="email" id="email" v-model="form.email" placeholder="Enter Email" />
      <input type="password" id="password" v-model="form.password" placeholder="****" />
      <button type="submit">Login</button>
    </form>
  </div>
</template>
