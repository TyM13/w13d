<template>
  <div id="app">
    <song-list></song-list>
    <play-list></play-list>
  </div>
</template>

<script>
import SongList from "@/components/SongList.vue";
import PlayList from "@/components/PlayList.vue";
export default {
  name: "App",
  components: {
    SongList,
    PlayList,
  },
};
</script>

<style>
</style>
