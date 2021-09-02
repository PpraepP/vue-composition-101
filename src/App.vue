<template>
  <section class="container">
    <UserData :firstname="firstname" :lastname="lastname"/>
    <button @click="setAge">change age</button>
    <div>
      <input type="text" placeholder="Firstname" v-model="firstname">
      <input type="text" placeholder="Lastname" ref="lastnameInput">
      <button @click="setLastname">Set Lastname</button>
    </div>
  </section>
</template>

<script>
import { ref, computed, watch, provide } from "vue";
import UserData from "@/components/UserData";
export default {
  components: { UserData },
  setup(){
    const uAge = ref(25);
    const firstname = ref('');
    const lastname = ref('');
    const lastnameInput = ref(null);

    //provide('keyname', value);
    provide('userAge', uAge);

    //computed(function() { //code here });
    const uName = computed(() => 
      `${firstname.value} ${lastname.value}`
    )

    // watch with muti value
    watch([uAge, uName], function(newVals, oldVals){
      console.log('old age', oldVals);
      console.log('new age', newVals)
    })

    function setNewAge(){
      // if use ref() => uAge.value = 25
      // if use reactive() => user.age = 25
      uAge.value = 26
    }

    function setLastname(){
      lastname.value = lastnameInput.value.value;
    }

    return { username: uName, age: uAge, setAge: setNewAge, setLastname, firstname, lastname, lastnameInput};
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
  // },
  // watch: {
  //   age(val){
  //     console.log('age is', val)
  //   }
  // },
  // provide(){
  //   return { age: this.age}
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