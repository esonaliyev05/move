<template>
  <div class="app font-monospace">
    <div class="content">
      <Appinfo :allMoviesCount="movies.length" :favouriteMoviesCount="movies.filter(c => c.favourite).length"/>
      <div class="serach-panel">
        <SearchPanel />
        <AppFilter />
      </div>
      <MovieList :movies="movies"/>
      <MovieAddForm />
    </div>
  </div>
</template>
<script>
import Appinfo from "../app-info/Appinfo.vue";
import SearchPanel from "../search-panel/SearchPanel.vue";
import AppFilter from "../app-filter/AppFilter.vue";
import MovieList from "../movie-list/MovieList.vue";
import MovieAddForm from "../movie-add-form/MovieAddForm.vue";

export default {
  components: {
    Appinfo,
    SearchPanel,
    AppFilter,
    MovieList,
    MovieAddForm,

  },
  data() {
    return {
      movies: [
        {
          name: "Omar",
          viewers: 511,
          favourite: false,
          like: true,
        },
        {
          name: "Alyorbek Esonaliyev",
          viewers: 411,
          favourite: false,
          like: false,
        },
        {
          name: "Ally oor",
          viewers: 811,
          favourite: true,
          like: false,
        },
      ],
    };
  },
};
</script>

<style>
.app {
  height: 100vh;
  color: black;
}

.app .content {
  width: 800px;
  min-height: 700px;
  background-color: #fff;
  margin: 0 auto;
  padding: 5px 10px;
  border: 1px solid black;
}

.content .serach-panel {
  margin-top: 2rem;
  padding: 1.5rem;
  background-color: #fcfaf5;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgb(0, 0, 0, 0.15);
}
</style>
