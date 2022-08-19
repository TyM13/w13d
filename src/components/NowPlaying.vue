<template>
  <div>
    <h1 class="now_playing">Now Playing</h1>
    <h2 class="now_playing" ref="playing_song"></h2>
  </div>
</template>
                                                              
<script>                                                      
export default {                                              // funtion playing songs that gets the ref from html and puts the innertext of playingsong (h2 tag) to song_title
  methods: {
    playing_song(song_title) {
      this.$refs[`playing_song`][`innerText`] = song_title;
    },
  },
  mounted() {                                                 // gets the emit from a different componenet by using now_playing and calls the function playing_song
    this.$root.$on(`now_playing`, this.playing_song);
  },
};
</script>

<style scoped>
.now_playing {
  text-align: center;
  margin-bottom: 0px;
}
</style>