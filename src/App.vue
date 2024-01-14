<script setup>
import { ref } from 'vue'
// two way bindings - take two different things: variable and html element. Tie them
// together and make them always equal to each other. 
//cors - cross origin resource sharing - if you go into a club, cors is the bouncer at the club

let email = ref('')
let password = ref('')


function login() { 
  const body = { 
    "email": "email.value", 
    "password": "password.value"
  }

  fetch("http://localhost:3000/login", {
      headers: {"Content-Type": "application/json"}, 
      body: JSON.stringify(reqBody)
    })
  .then(response => {
    return response.json
  })
  .then(json => { 
    console.log(json)

    //Do Stuff
  })
  .catch(error => { 
    console.log(error)
  })
}
</script>

<template>
  <div class="container"></div>
    <img src="https://img.freepik.com/premium-vector/modern-badge-logo-instagram-icon_578229-124.jpg">
    <input v-model="email" type="text" placeholder="email"/>
    <input v-model="password" type="text" placeholder="password">
    <button @click="login">Login</button>
    <button>Register</button>
</template>


<style scoped>
.container { 
  display: flex; 
  flex-direction: column; 
  align-items: center; 
  justify-content: center; 
  gap: 10px;
  height: 100vh;  
  
}
#logo {
  height: 6rem; 
  widows: 6rem; 
}

</style>
