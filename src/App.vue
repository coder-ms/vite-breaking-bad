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
import { store } from './store';

// SCRIPT EXPORT DEFAULT
export default {
  components: {
    AppHeader,
    AppSearch,
    CharacterList,
  },
  data() {
    return {
      store,
      endPoint: 'character',
    }
  },

  methods: {
    getCharacters() {
      store.errormessage = '';
      let options = null;

      if (store.search.status && store.search.name) {
        options = {
          params: {
            status: store.search.status,
            name: store.search.name
          }
        }
      } else if (store.search.status) {
        options = {
          params: {
            status: store.search.status
          }
        }
      } else if (store.search.name) {
        options = {
          params: {
            name: store.search.name
          }
        }
      }
      store.loading = true;

      //
      const apiurl = store.apiURL; //  + this.endPoint;

      //
      if ((null != options))
        if ((null != options.params)) {
          console.log('options.params.name = ' + options.params.name);
          console.log('options.params.status = ' + options.params.status);
        }
      console.log('endPoint = ' + this.endPoint);
      console.log('apiurl = ' + apiurl);

      //
      axios.get(apiurl, options).then(
        (res) => {
          store.characterList = res.data;
          store.loading = false;
        }
      ).catch((error) => {
        store.characterList.length = 0;
        store.loading = false;
        store.errormessage = error.message
        // console.log(error.message);
        // console.log(error.response.status);
      })
    }
  },
  created() {
    this.getCharacters()
  }
}
</script>

<style lang="scss" scoped>

</style>
