<template>
    <h2>{{ userName }}</h2>
    <h3>{{ age }}</h3>
</template>
<script>
import { computed } from "vue";
export default {
    props: ['firstname', 'lastname', 'age'],
    setup(props){
        console.log('props', props);
        const userName = computed(() => props.firstname +' '+ props.lastname)
        return { userName }
    }
    // computed:{
    //     userName(){
    //         return this.firstname +' '+this.lastname;
    //     }
    // }
}
</script>