<template>
  <h2>My Course Goal</h2>
  <!-- Task 1: Output your main course goal with help of the composition API -->
  <!-- Don't hardcode it into the template, instead hardcode it into the JS code -->
  <!-- <h3 v-if="onShow">{{goal}}</h3> -->
  <!-- <h3 v-if="goals.onShow">{{goals.myGoal}}</h3> -->
  <h3 v-if="onShow">{{myGoal}}</h3>
  <!-- Task 2: Toggle (show/ hide) the goal with help of the button  -->
  <button @click="onToggle">Toggle Goal</button>
  <!-- Task 3: Manage data in three ways -->
  <!-- => Separate refs -->
  <!-- => Ref Object -->
  <!-- => Reactive Object -->
  <!-- Task 4: Also solve the assignment with the Options API -->
</template>

<script>
// import { reactive } from "vue";
export default {
  // setup(){
  //   // const myGoal = ref('I can work be nice!');
  //   // const onShow = ref(true);

  //   // const courseDataRefs = ref({
  //   //   myGoal: 'I can work be nice!',
  //   //   onShow: true
  //   // })

  //   const courseDataReacetive = reactive({
  //     myGoal: 'I can work be nice!',
  //     onShow: true
  //   })

  //   function toggleMenu(){
  //     console.log('onToggle', courseDataReacetive.onShow);
  //     // onShow.value = !onShow.value;
  //     // courseDataRefs.value.onShow = !courseDataRefs.value.onShow;
  //     courseDataReacetive.onShow = !courseDataReacetive.onShow;
  //   }
  //   return{ goals: courseDataReacetive, onToggle: toggleMenu }
  // }
  data: () => ({
    myGoal: 'I can work be nice!',
    onShow: true
  }),
  methods: {
    onToggle(){
      console.log('onToggle');
      this.onShow = !this.onShow
    }
  }
}
</script>

<style>
html {
  font-family: sans-serif;
}
body {
  margin: 3rem;
  text-align: center;
}
</style>