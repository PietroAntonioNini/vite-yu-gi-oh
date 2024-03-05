<script>
import { store } from '../store';

export default {
    name: 'CardSearch',

    data() {
        return {
            store,
        }
    },
}
</script>

<template>
    
    <select name="type" id="type" @change="$emit('option')" v-model="store.selectedArchetype">
        <option :value="archetype.archetype_name" v-for="archetype in store.archetypes">{{ archetype.archetype_name }}</option>
    </select>

</template>

<style lang="scss">

#type {
    width: 240px;
    margin: 30px 10px;
    padding: 10px;

    border: 0;
    border-radius: 8px;
        
    color: black;
    background-color: white;
}

</style>
