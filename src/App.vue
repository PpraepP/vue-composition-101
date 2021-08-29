<template>
  <section class="container">
    <h2>{{ user.name }}</h2>
    <h3>{{ user.age }}</h3>
    <button @click="setAge">change age</button>
  </section>
</template>

<script>
import { reactive } from "vue";
export default {
  setup(){
    // const uName = ref("PpraepP");
    // const uAge = ref(25);

    const user = reactive({
      name: "PpraepP",
      age: 25
    })
    
    setTimeout(() => {
      // if use ref => uName.value = 'Prae' 
      // if use ref => uAge.value = '26' 
      user.name = 'Prae';
      user.age = 26
    }, 2000)

    function setNewAge(){
      // if use ref() => uAge.value = '25
      user.age = 25
    }

    return { user: user, setAge: setNewAge}
  },
  // data() {
  //   return {
  //     userName: 'Maximilian',
  //      age: 20
  //   };
  // },
  // methods: {
  //   setAge(){
  //     this.age = 25
  //   }
  // }
};
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}

.container {
  margin: 3rem auto;
  max-width: 30rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 1rem;
  text-align: center;
}
</style>