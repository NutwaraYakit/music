<template>
  <div class="col">
    <b-col cols="12">
      <br><br>
      <input id="ss" type="text" v-model="textSearch" placeholder=" Search..." />
      <button id="bts" @click="searchData()">Search</button>
    </b-col>
    <br><br>
    <b-row>
      <b-col id="ms" cols="10">
        <div class="mt-4" v-for="list in playList" :key="list.trackId">
          <b-card
            no-body
            class="overflow-hidden"
            style="width: 100%"
            border-variant="info"
          >
            <b-row id="bb" no-gutters >
              
              <b-col md="3">
                <b-card-img
                  :src="list.artworkUrl60"
                  :alt="list.artistName"
                  class="rounded-0"
                ></b-card-img>
              </b-col>
              <b-col md="8">
                <b-card-body :title="list.trackName">
                  {{ list.trackId }}
                <b-card-text>
                    <audio controls>
                      <source :src="list.previewUrl" type="audio/mpeg" />
                    </audio>
                    <b-card-text :title="list.releaseDate">
                      {{ list.releaseDate }}
                    </b-card-text>
                    <b-card-text :title="list.shortDescription">
                      {{ list.shortDescription }}
                    </b-card-text>
                  </b-card-text>
                </b-card-body>
              </b-col>
            </b-row>
          </b-card>
        </div>
      </b-col>
    </b-row>
  </div>
</template>
<script>
import axios from "axios";
export default {
  data() {
    return {
      playList: null,
      textSearch: "",
    };
  },
  methods: {
    searchData() {
      axios
        .get(
          "https://itunes.apple.com/search?term=+" +
            this.textSearch +
            "&limit=100"
        )
        .then((response) => {
          this.playList = response.data.results.slice(0, 20);
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>
<style>
#text {
  color: rgb(0, 0, 0);
}
#ss{
  border-radius: 15px;
  width: 350px;
  height: 50px;
  margin: 6px;
  background-color: rgb(235, 235, 235);
  border: 2px solid  rgb(235, 235, 235);
}
#bts{
  border-radius: 15px;
  width: 100px;
  height: 50px;
  background-color: rgba(207, 31, 119, 0.863);
  border: 2px solid  rgba(207, 31, 119, 0.863);
  color: aliceblue;
}
#ms{
  justify-content: center;
  padding-left: 200px;
}
#bb{
  background-color: rgba(221, 77, 185, 0.678);
  border: 2px solid  rgba(255, 255, 255, 0.863);
}
</style>