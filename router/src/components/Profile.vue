<template>
<h1> User {{profile}} 's Profile Page</h1>
</template>

<script>
import {useRoute} from 'vue-router'
export default {
    name: "ProfileComponent",
    data(){
        return {
            profile : ''
        }
    },
    mounted(){
        const route = useRoute();
        console.warn('route', route.params.id);
        this.profile = route.params.id;
    }
}
</script>

<style>

</style>
