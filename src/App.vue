<script>
import axios from 'axios';
import { store } from './store';
import CardList from './components/CardList.vue';

export default {
    data() {
        return {
            store,
        }
    },

    created() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0').then(res => {
            console.log(res.data.data);
            this.store.cards = res.data.data
        })
    },

    components: {
        CardList,
    }
}
</script>

<template>
  <CardList></CardList>
</template>

<style>
</style>
