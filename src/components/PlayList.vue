<template>
  <div>
    <section @click="now_playing" class="songs_clicked">
      <h1>Play List</h1>
    </section>
  </div>
</template>

<script>                                                                  // (above) when something in the section is clicked it will call the function now_playing
export default {                                                          // (below) gets the section class and sets it to the variable selected_songs 
  methods: {                                                              // inserts song title in the selected songs tag
    show_playlist_song(song_title) {
      let selected_songs = document.querySelector(`.songs_clicked`);
      selected_songs.insertAdjacentHTML(
        `beforeend`,
        `<h3 class="songs_clicked">${song_title}</h3>`
      );
    },
    now_playing(details) {                                                // (below) function that gets the info of details target innertext and sets it to song_title
      let song_title = details[`target`][`innerText`];                    // takes song title and emits it so other components can get the info if now_playing is used
      this.$root.$emit(`now_playing`, song_title);
    },
  },

  mounted() {                                                             // gets the emit from a different componenet by using user_clicked and calls the function show_playlist_song
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