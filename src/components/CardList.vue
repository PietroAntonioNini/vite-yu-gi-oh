<script>
import { store } from '../store';

export default {
    name: 'CardList',

    data() {
        return {
            store,
        }
    },
}
</script>

<template>
    <div class="container">
        <nav id="card-nav">
            <h2 id="nav-text">Found 39 cards</h2>
        </nav>

        <ul id="cards-container">
            <li id="cards-box" v-for="card in store.cards">
                
                <h3>{{ card.name }}</h3>
                <h4>{{ card.archetype }}</h4>
            </li>
        </ul>
        
    </div>
</template>

<style lang="scss">

.container {
    padding: 70px;
    background-color: white;

    #card-nav {
        padding: 20px;
        background-color: #222529;

        #nav-text {
            color: white;
        }
    }

    #cards-container {
        display: flex;
        flex-flow: row wrap;
        gap: 30px;

        #cards-box {
            width: calc(100% / 5 - 30px/5 * 4);

            display: flex;
            flex-direction: column;
            text-align: center;
            gap: 20px;

            background-color: #D48F38;

            h3 {
                font-size: 24px;
                font-weight: bold;
                text-transform: uppercase;
            }

            h4 {
                font-size: 28px;
                font-weight: 400;
                color: black;
            }
        }
    }
}

</style>
