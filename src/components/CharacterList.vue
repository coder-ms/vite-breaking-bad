
<template>
    <div v-if="loading">
        Sto caricando i dati
    </div>
    <div class="struct" v-if="!loading">
        <div class="cardSection" v-for="(item, index) in characters" :key="item.id">
            <CardComponent :character="item" />
        </div>
    </div>
</template>

<script>
import CardComponent from './CardComponent.vue';
export default {
    name: "CharacterList",
    props: ["characters", "loading"],
    components: { CardComponent }
}
</script>

<style lang="scss" scoped>
.struct {
    width: 70%;
    margin: 0 auto;
    background-color: green;
    display: flex;
    flex-wrap: wrap;

    .cardSection {
        width: 20%;
        border: 1px solid black;
        padding: 10px;
        text-align: center;
    }
}
</style>