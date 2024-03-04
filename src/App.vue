<script>
import axios from 'axios';

export default {
    data() {
        return {
            
        }
    },

    created() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0').then(res => {
            console.log(res.data.data);
        })
    },

    components: {

    }
}
</script>

<template>
  
</template>

<style>
</style>
