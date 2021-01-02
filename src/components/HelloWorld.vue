<template>
  <h1>Search articles from LearnVue</h1>
  <div>
    <input 
      type="text"
      placeholder="Search for articles"
      v-model="query"
    />
    <button @click="reset"> Reset </button>  
   </div>
   <search-results :query="query"/>
</template>

<script>
import { ref } from 'vue';
import SearchResults from './SearchResults.vue';

export default {
  components: {
    SearchResults
  },

  setup () {
    const query = ref('');

    const reset = () => {
      query.value = '';
    }

    return {
      query,
      reset
    }
  }
}

</script>
