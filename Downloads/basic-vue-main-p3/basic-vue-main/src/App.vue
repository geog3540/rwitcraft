<template>
  <div class="search-container">
    <h1>Advanced Movie Search</h1>
    <form @submit.prevent="submitForm">
      <section class="genre">
        <h2>Genre</h2>
        <div v-for="genre in genres" :key="genre">
          <input type="checkbox" :id="genre" :value="genre" v-model="searchParams.genres">
          <label :for="genre">{{ genre }}</label>
        </div>
      </section>

      <div class="year-released">
        <h2>Year Released</h2>
        <input type="number" v-model.number="searchParams.yearMin" placeholder="Min">
        <input type="number" v-model.number="searchParams.yearMax" placeholder="Max">
      </div>

      <div class="imdb-rating">
        <h2>IMDB Rating</h2>
        <input type="number" step="0.1" v-model.number="searchParams.imdbMin" placeholder="Min (1-10)">
        <input type="number" step="0.1" v-model.number="searchParams.imdbMax" placeholder="Max (1-10)">
      </div>


      <button type="submit">Search</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      genres: ['Action', 'Adventure', 'Drama', ],
      searchParams: {
        genres: [],
        yearMin: null,
        yearMax: null,
        imdbMin: null,
        imdbMax: null,
      }
    };
  },
  methods: {
    submitForm() {
      console.log(this.searchParams);
    }
  }
};
</script>

<style>

</style>
