<template>
  <div id="app">
    <!-- Include the UserInput component -->
    <UserInput @query-submitted="handleQuerySubmitted" />
    <!-- Display the search results below the input field -->
    <!-- For now, let's display a simple message -->
    <div v-if="searchResults">
      <h2>Search Results:</h2>
      <ul>
        <li v-for="(result, index) in searchResults" :key="index">{{ result }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
import UserInput from './components/UserInput.vue';

export default {
  components: {
    UserInput,
  },
  data() {
    return {
    searchResults: null,
    };
  },
  methods: {
    handleQuerySubmitted(query) {
      // dummy search result data
    // later we integrate the backend and video search API
      this.searchResults = [
        `Dummy video 1 for query: "${query}"`,
        `Dummy video 2 for query: "${query}"`,
        `Dummy video 3 for query: "${query}"`,
      ];
    },
  },
};
</script>