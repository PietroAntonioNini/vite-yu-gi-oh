<script>
import axios from 'axios';
import { store } from './store';
import CardList from './components/CardList.vue';
import CardSearch from './components/CardSearch.vue';

export default {
    data() {
        return {
            store,
        }
    },

    created() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=40&offset=0').then(res => {
            this.store.cards = res.data.data;
        });

        axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php').then(res => {
            this.store.archetypes = res.data;
        });
    },

    components: {
        CardList,
        CardSearch,
    },

    methods: {
        optionSelect() {

            let url = 'https://db.ygoprodeck.com/api/v7/cardinfo.php?';

            if (this.store.selectedArchetype != 0) {
                url += 'archetype=' + this.store.selectedArchetype;

            } else {
                url += 'num=40&offset=0';
            }

            axios.get(url).then(res => {
                this.store.cards = res.data.data
            });

        },
    },
}
</script>

<template>
    <nav>
        <img class="logo" src="/img/Yu-Gi-Oh!-logo.png" alt="logo Yu-Gi-Oh">
        <h1>Yu-Gi-Oh Api</h1>
    </nav>

    <main>
        <CardSearch @option="optionSelect()"></CardSearch>
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

    
}

</style>
