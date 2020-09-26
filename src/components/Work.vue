<template>
<div>
    <img src="https://cdn.iconscout.com/icon/free/png-512/google-play-music-2038774-1721661.png" alt="" height="50px" width="200px" class="img-fluid mx-auto" />
    <br />
    <br />
    <div class="row">
        <div class="col">
        </div>
        <div class="col">
            <input class="form-control ds-input " type=" text" v-model="keyword" placeholder="กรุณากรอกชื่อเพลง" />
            <br />
            <button @click="searchData" class="btn btn-danger">ค้นหา</button>
            <!--{{resultData}} -->
        </div>
        <div class="col">
        </div>
    </div>
    <br />
    <br />
    <div class="container">
    <div class="row">
        <div class="col-sm">
            <b-card-group columns>
                <div v-for="data in resultData" :key="data.trackId">
                    <b-card :title="data.title" :img-src="data.artworkUrl100" img-alt="Image" img-top tag="article" style="max-width: 25rem;" class="mb-2">
                        <b-card-text>{{ data.trackName }}</b-card-text>
                        <b-card-text>{{ data.artistName }}</b-card-text>
                        <audio controls >
                            <source :src="data.previewUrl" type="audio/mpeg" />
                        </audio>
                        <b-button :href="data.trackViewUrl" variant="danger">Play</b-button>
                    </b-card>
                </div>
            </b-card-group>
        </div>
    </div>
    </div>
</div>
</template>

<script>
import axios from "axios";
export default {
    data() {
        return {
            resultData: null,
            keyword: "",
        };
    },
    methods: {
        searchData() {
            axios
                .get(
                    "https://itunes.apple.com/search?term=" + this.keyword + "&limit=15"
                )
                .then((response) => {
                    this.resultData = response.data.results;
                })
                .catch((err) => {
                    console.log(err);
                });
        },
    },
};
</script>

<style>
.card {
    background-image: url('https://sweet-summer.com/wp-content/uploads/2020/04/SweetSummer_background_Majory-700x394.jpg');
}
</style>
