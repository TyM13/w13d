<template>
  <div id="app">
    <now-playing></now-playing>
    <play-list></play-list>
    <song-list></song-list>
  </div>
</template>

<script>
import SongList from "@/components/SongList.vue";
import PlayList from "@/components/PlayList.vue";
import NowPlaying from "@/components/NowPlaying.vue";
export default {
  name: "App",
  components: {
    SongList,
    PlayList,
    NowPlaying,
  },
};
</script>

<style>
</style>
