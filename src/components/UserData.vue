<template>
    <h2>{{ userName }}</h2>
    <h3>{{ age }}</h3>
</template>
<script>
import { computed, inject } from "vue";
export default {
    props: ['firstname', 'lastname'],
    setup(props, ctx){
        console.log('props', props);
        console.log('context', ctx);

        const age = inject('userAge');

        // ctx.emit('save-data', 1); // this.$emit('save-data', 1);

        const userName = computed(() => props.firstname +' '+ props.lastname)

        return { userName, age }
    }
    // computed:{
    //     userName(){
    //         return this.firstname +' '+this.lastname;
    //     }
    // }
}
</script>