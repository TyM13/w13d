<template>
  <div>
    <section ref="song_clicked" class="songs_clicked"></section>
  </div>
</template>

<script>
export default {
  methods: {
    show_playlist_song(song_title) {
      let selected_songs = document.querySelector(`songs_clicked`);
      selected_songs.insertAdjacentHTML(
        `afterbegin`,
        `<h1 class="songs_clicked">${song_title}</h1>`
      );
    },
  },

  mounted() {
    this.$root.$on(`user_clicked`, this.show_playlist_song);
  },
};
</script>

<style scoped>
</style>