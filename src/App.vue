<template>
  <section class="container">
    <h2>{{ username }}</h2>
    <button @click="setAge">change age</button>
    <div>
      <!-- use function -->
      <!-- <input type="text" placeholder="Firstname" @input="setFirstname">
      <input type="text" placeholder="Lastname" @input="setLastname"> -->
      <input type="text" placeholder="Firstname" v-model="firstname">
      <input type="text" placeholder="Lastname" v-model="lastname">
    </div>
  </section>
</template>

<script>
import { ref, reactive, computed } from "vue";
export default {
  setup(){
    // const uName = ref("PpraepP");
    // const uAge = ref(25);
    const firstname = ref('');
    const lastname = ref('');

    const user = reactive({
      name: "PpraepP",
      age: 25
    })

    //computed(function() { //code here });
    const uName = computed(() => 
      `${firstname.value} ${lastname.value}`
    )

    function setNewAge(){
      // if use ref() => uAge.value = '25
      user.age = 25
    }

    // function setFirstname(evt){
    //   firstname.value = evt.target.value;
    // }

    // function setLastname(evt){
    //   lastname.value = evt.target.value;
    // }

    return { username: uName, setAge: setNewAge, setFirstname, setLastname, firstname, lastname}
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