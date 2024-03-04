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

        <div id="card-box">
            
        </div>
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
}

</style>
