<template>
  <div>
    <div ref="song_container" v-for="song in songs" :key="song[`song_id`]">
      <h1 @click="add_to_playlist">{{ song[`title`] }}</h1>

      <h2>
        {{ song[`artist`] }}
      </h2>
      <section><img :src="song[`img_url`]" /></section>
    </div>
  </div>
</template>

<script>                                              // (above) a for loop that loops through songs, through the key song[song_id] // added a click that calls the function add_to_playlist when the song title is clicked
export default {                                      // (below) function that gets the info of details target innertext and sets it to song_title
  methods: {                                          // takes song title and emits it so other components can get the info if user_clicked is used
    add_to_playlist(details) {                        
      let song_title = details[`target`][`innerText`];
      this.$root.$emit(`user_clicked`, song_title);
    },
  },

  data() {                                            // array of objects that contain key:value pairs
    return {
      songs: [
        {
          title: `It aint me`,
          artist: `Kygo, Selena Gomez`,
          song_id: 1,
          img_url: `https://upload.wikimedia.org/wikipedia/en/d/d3/It_Ain%27t_Me_%28Official_Single_Cover%29_by_Kygo_%26_Selena_Gomez.png`,
        },
        {
          title: `Over The Edge `,
          artist: `Tristam`,
          song_id: 2,
          img_url: `https://i1.sndcdn.com/artworks-OYEcCTq3XCtl-0-t500x500.jpg`,
        },
        {
          title: `Time Of Your Life`,
          artist: `Green Day`,
          song_id: 3,
          img_url: `https://upload.wikimedia.org/wikipedia/en/1/13/Green_Day_-_Good_Riddance_%28Time_of_Your_Life%29_cover.jpg`,
        },
      ],
    };
  },
};
</script>

<style scoped>
img {
  width: 200px;
}
</style>