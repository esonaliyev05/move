<template>
  <div class="movie-add-form">
    <h3>Yangi kino qoshish</h3>
    <form class="add-form d-flex" @submit.prevent>
      <input
        type="text"
        class="form-control new-label"
        placeholder="qanday kino"
        :value="name"
        @input="name = $event.target.value"
      />
      <input
        type="number"
        class="form-control new-label"
        placeholder="Nechi Marotaba ko'rilgan"
        :value="viewers"
        @input="viewers = $event.target.value"
      />
      <button class="btn btn-outline-dark" @click="addMovie">qo'shish</button>
    </form>
  </div>
</template>
<script>
export default {
  data() {
    return {
      name: "",
      viewers: "",
    };
  },
  methods: {
    addMovie() {
      if(!this.name || !this.viewers) return
      const newMovie = {
        name: this.name,
        viewers: this.viewers,
        favourite: false,
        like: false,
        id: Date.now(),


      };
      this.$emit("createMovie" , newMovie)
      this.name = '',
      this.viewers = ''

    },
  },
};
</script>
<style>
.movie-add-form {
  margin-top: 2rem;
  margin-bottom: 1rem;
  padding: 1.5rem;
  background-color: #fcfaf5;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgb(0, 0, 0, 0.15);
}
</style>
