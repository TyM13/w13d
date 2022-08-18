<template>
  <div>
    <song-list>
      <h1 ref="song_clicked" @user_clicked="show_playlist_song"></h1>
    </song-list>
  </div>
</template>

<script>
export default {
  methods: {
    show_playlist_song(song_title) {
      this.$refs[`song_clicked`][`innerText`] = song_title;
    },
  },

  mounted() {
    this.$root.$on(`user_clicked`, this.show_playlist_song);
  },
};
</script>

<style scoped>
</style>