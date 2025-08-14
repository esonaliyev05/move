<template>
  <ul class="movie-list list-group">
    <MoveListItem v-for="movie in movies" v-bind:movie="movie" :key="movie.id" 
    @onToggle="$emit('onToggle' , $event)" 
    @onRemove="$emit('onRemove' , movie.id)"
    
    />
  </ul>
</template>
<script>
import MoveListItem from "../movie-list-item/MoveListItem.vue";
export default {
  components: { MoveListItem },
  props: {
    movies: {
      type: Array,
      required: true,

    }
  }

};
</script>
<style>
.movie-list {
  margin-top: 2rem;
  margin-bottom: 1rem;
  padding: 1.5rem;
  background-color: #fcfaf5;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgb(0, 0, 0, 0.15);
}
</style>
