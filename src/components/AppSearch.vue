<template>
    <div class="container">
        <!--FORM-->
        <form class="row row-cols-lg-auto g-3 align-items-center" @submit.prevent="searchCharacters">
            <div class="col-12">
                <label class="visually-hidden" for="charactername">Search name</label>
                <input type="text" class="form-control" id="charactername" placeholder="Search name"
                    v-model.trim="store.search.name">
            </div>

            <!--SELECT STATUS-->
            <div class="col-12">
                <label class="visually-hidden" for="searchStatus">Search status</label>
                <select class="form-select" id="searchStatus" v-model="store.search.status">
                    <option selected value="">Choose...</option>
                    <option :value="status" v-for="(status, index) in statusOptions" :key="index">{{ status }}</option>
                </select>
            </div>

            <!--BUTTON SUBMIT-->
            <div class="col-12">
                <button type="submit" class="btn btn-primary">Search</button>
            </div>

            <!--BUTTON RESET-->
            <div class="col-12">
                <button type="reset" class="btn btn-primary" @click="resetSearch">Reset</button>
            </div>
        </form>
    </div>

</template>

<script>
import { store } from '../store';

export default {
    name: 'AppSearch',
    data() {
        return {
            store,
            statusOptions: [
                'alive',
                'dead',
                'unknown'
            ],
        }
    },
    methods: {
        searchCharacters() {
            this.$emit('filterchar');
        },
        resetSearch() {
            store.search.status = '';
            store.search.name = '';
            this.$emit('filterchar')
        }
    }
}
</script>

<style lang="scss" scoped>
.container {
    display: flex;
    color: white;
    justify-content: center;
    align-items: center;
    padding-bottom: 10px;

    form {
        justify-content: space-between;
    }
}
</style>
