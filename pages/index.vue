<template>
  <h1>Login to enter the petting zoo:</h1>
  <input type="text" placeholder="Username Here:" v-model="state.username"/>
  <br /><br />
  <input type="password" placeholder="Password Here:" v-model="state.password" />
  <br /> <br />
  <button @click="performLogin">Log in!</button>
</template>

<script setup>
  const state = reactive({
    username: "",
    password: ""
  });

  async function performLogin(){
    const response = await $fetch("/api/login", {
      method: "post",
      body: state
    });
    if(response){
      navigateTo("/zoo");
    }
  }
</script>

<style>
* {
  font-family: sans-serif;
}
</style>
