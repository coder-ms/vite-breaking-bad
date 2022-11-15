
<template>
    <div v-if="store.loading">
        Sto caricando i dati
    </div>
    <div class="struct" v-if="!store.loading">
        <div class="cardSection" v-for="(item, index) in store.characterList" :key="item.id">
            <CardComponent :character="item" />
        </div>
    </div>
</template>

<script>

import { store } from '../store';
import CardComponent from './CardComponent.vue';

export default {
    name: "CharacterList",
    components: { CardComponent },
    data() {
        return {
            store
        }
    }
}
</script>

<style lang="scss" scoped>
.struct {
    width: 70%;
    margin: 0 auto;
    background-color: white;
    padding: 40px 30px;
    display: flex;
    color: white;
    justify-content: space-between;
    flex-wrap: wrap;
    margin-top: 20px;

    .cardSection {
        width: 15%;
        border: 1px solid black;
        padding: 10px;
        margin-bottom: 10px;
        text-align: center;
        background-color: rgb(15, 28, 48);
    }
}
</style>