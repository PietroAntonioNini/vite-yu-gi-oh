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
            this.store.cards = res.data.data;
        })
    },

    components: {
        CardList,
    }
}
</script>

<template>
    <nav>
        <img class="logo" src="/img/Yu-Gi-Oh!-logo.png" alt="logo Yu-Gi-Oh">
        <h1>Yu-Gi-Oh Api</h1>
    </nav>

    <main>
        <select name="type" id="type">
            <option value="alien">Alien</option>
        </select>

        <CardList></CardList>
    </main>
</template>

<style lang="scss">

nav {
    display: flex;
    align-items: center;
    padding: 10px 50px;

    background-color: white;

    .logo {
        width: 80px;
        margin-right: 30px;
    }

    h1 {
        font-size: 60px;
        font-weight: 400;
        color: black;
    }
    
}

main {
    padding: 0 160px;

    background-color: #D48F38;

    #type {
        width: 240px;
        margin: 30px 10px;
        padding: 10px;

        border: 0;
        border-radius: 8px;
        
        color: black;
        background-color: white;
    }
}

</style>
