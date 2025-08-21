<template>
  <div class="app font-monospace">
    <div class="content">
      <Appinfo :allMoviesCount="movies.length" :favouriteMoviesCount="movies.filter(c => c.favourite).length"/>
      <div class="serach-panel">
        <SearchPanel :updateTermHandler="updateTermHandler  "  />
        <AppFilter :updateFilterHandler="updateFilterHandler" :filterName="filterName" />
      </div>
      <MovieList
       :movies="onFilterHandler(onSearchHandler(movies , term), filter )"
         @onToggle='onToggleHandler'
        @onRemove="onRemoveHandler"  />
      <MovieAddForm  @createMovie="createMovie" />
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
          like: false,
          id: 1,
        },
        {
          name: "Alyorbek Esonaliyev",
          viewers: 411,
          favourite: false,
          like: false,
          id: 2,
        },
        
      ],
     term: '',
     filter: 'all',

    };
  },

  methods:{
     createMovie(item) {
      this.movies.push(item)

     },
     onToggleHandler({id , prop}) {
        this.movies = this.movies.map(item => {
       if (item.id === id) {
         return { ...item, [prop]: !item[prop] };
       }
    return item;
  });
},

onRemoveHandler(id) {
  this.movies = this.movies.filter(c => c.id !== id)
},

onSearchHandler(arr, term){
  if (term.length == 0) {
    return arr
    
  }
  return arr.filter(c => c.name.toLowerCase().indexOf(term) > -1)
},

onFilterHandler(arr , filter) {
  
  switch (filter) {
    case 'popular':
      
      return arr.filter(c => c.like)

      case "mostVieers":
        return arr.filter(c => c.viewers > 500)

    default:
      return arr;
  }
 

},

updateTermHandler(term){
   this.term = term

},

updateFilterHandler(filter) {
  this.filter = filter

}
}
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
