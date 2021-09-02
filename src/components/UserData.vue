<template>
    <h2>{{ userName }}</h2>
    <h3>{{ age }}</h3>
</template>
<script>
import { computed } from "vue";
export default {
    props: ['firstname', 'lastname', 'age'],
    setup(props, ctx){
        console.log('props', props);
        console.log('context', ctx);

        // ctx.emit('save-data', 1); // this.$emit('save-data', 1);

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