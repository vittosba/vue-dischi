<template>
  <section class='album-list py-5'>
      <div class="container">
          <div class="row">
            <div v-for="(album, index) in albumList" :key="`album-${index}`" class="col-6 col-md-4 col-lg-2 mb-5">
                    <!-- Card -->
                    <Card 
                        :image="album.poster"
                        :title="album.title"
                        :subTitle="album.author"
                        :subTitle2="album.year"
                        :text="album.genre" 
                    />
                </div>
          </div>
      </div>
  </section>
</template>

<script>
import axios from 'axios';
import Card from '@/components/Card.vue';

export default {
    name: 'AlbumList',
    components: {
        Card,
    },
    data() {
        return {
            albumList: null,
        }
    },
    created() {
        this.getAlbums();
    },
    methods: {
        getAlbums() {
            /**
             * Get album from API
             */
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(result => {
                console.log(result.data.response);
                this.albumList = result.data.response;
            })
            .catch(err => console.log(err));
        }
    }
}
</script>

<style scoped lang='scss'>
@import '@/styles/variables';

    .album-list {
        background: $bg-pri-col;
        color: $text-pri-color;
    }

</style>