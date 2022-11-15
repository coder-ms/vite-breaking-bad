<!--TEMPLATE HTML GENERALE-->
<template>
  <AppHeader title="Breaking Bad API" />
  <main>
    <AppSearch @filterchar="getCharacters" />
    <CharacterList />
    <div v-if="store.errormessage">
      <h1> Opps ! Qualcosa è andato storto</h1>
      <p>{{ store.errormessage }}</p>
    </div>

  </main>

</template>

<script>

// IMPORT
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppSearch from './components/AppSearch.vue';
import CharacterList from './components/CharacterList.vue';

// SCRIPT EXPORT DEFAULT
export default {
  components: {
    AppHeader,
    AppSearch,
    CharacterList
  },
  data() {
    return {
      apiURL: 'https://www.breakingbadapi.com/api/characters',
      characterList: [],
      loading: false,
      searchType: ''
    }
  },
  methods: {
    getCharacters() {
      this.loading = true;
      axios.get(this.apiURL).then(
        (res) => {
          this.characterList = [...res.data];
          console.log(this.characterList)
          this.loading = false;
        }
      ).catch((error) => {
        this.loading = false;
        console.log(error);
      })
    }
  },
  created() {
    this.getCharacters();
  }
}
</script>

<style lang="scss" scoped>

</style>
