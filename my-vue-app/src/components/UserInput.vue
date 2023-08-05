/*  creating a reusable Vue component called UserInput.vue that will contain a text input field to take user queries.
This component will be responsible for capturing user input and emitting an event with the entered query 
when the user presses Enter or clicks a "Submit" button. */

<template>
  <div>
    <input v-model="userQuery" @keyup.enter="submitQuery" placeholder="What do you want to learn..." />
    <!-- optional button to submit the query if you prefer -->
    <button @click="submitQuery">Share</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      userQuery: '',
    };
  },
  methods: {
    submitQuery() {
      // Emit an event to notify the parent component with the user query
      this.$emit('query-submitted', this.userQuery);
      // clear the input field after submitting the query
      this.userQuery = '';
    },
  },
};
</script>