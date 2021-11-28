<template>
  <div id="app">
    <Header @performSearch="searchGeneres"/>

    <AlbumList :albumList="filteredGenere"/>
  </div>
</template>

<script>
import axios from 'axios';
import Header from '@/components/Header.vue';
import AlbumList from '@/components/AlbumList.vue';

export default {
  name: 'App',
  components: {
    Header,
    AlbumList,
  },
  data() {
    return {
        albumList: null,
        searchText: '',

    }
  },
  computed: {
    filteredGenere() {

		console.log('computed');
      if (this.searchText === '') {
        return this.albumList;
      }

      return this.albumList.filter(item => {
        // console.log(item.genre);
        if(item.genre.toLowerCase() === this.searchText.toLowerCase()) {
          return item.genre.toLowerCase();
        }
      });
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
    },
    searchGeneres(text) {
      console.log(text);
      this.searchText = text;
    },
  } 
}
</script>

<style lang="scss">
@import '@/styles/globals';

</style>
