<template>
  <div>
    <section class="songs_clicked"><h1>Play List</h1></section>
  </div>
</template>

<script>
export default {
  methods: {
    show_playlist_song(song_title) {
      let selected_songs = document.querySelector(`.songs_clicked`);
      selected_songs.insertAdjacentHTML(
        `beforeend`,
        `<h3 class="songs_clicked">${song_title}</h3>`
      );
    },
  },

  mounted() {
    this.$root.$on(`user_clicked`, this.show_playlist_song);
  },
};
</script>

<style scoped>
section {
  display: grid;
  place-items: center;
}
</style>