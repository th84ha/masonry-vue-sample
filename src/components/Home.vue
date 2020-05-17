<template>
  <div class="hello">
    <h1>Masonry Vue</h1>
    <div v-masonry item-selector=".item" class="masonry-container">
      <div v-masonry-tile class="item image" v-bind:key="index" v-for="(item, index) in items"><img :src="item"></div>
    </div>
  </div>
</template>

<script>

import Vue from 'vue'
import {VueMasonryPlugin} from 'vue-masonry'
Vue.use(VueMasonryPlugin)

export default {
  name: 'MasonryVue',
  data () {
    return {
      items: [
        '/static/images/01.jpg',
        '/static/images/02.jpg',
        '/static/images/03.jpg',
        '/static/images/04.jpg',
        '/static/images/05.jpg',
        '/static/images/06.jpg',
        '/static/images/07.jpg',
        '/static/images/08.jpg',
        '/static/images/09.jpg',
        '/static/images/10.jpg',
        '/static/images/11.jpg',
        '/static/images/12.jpg',
        '/static/images/13.jpg',
        '/static/images/14.jpg',
        '/static/images/15.jpg'
      ]
    }
  },
  mounted: function () {
    this.$redrawVueMasonry()
  },
  methods: {
    reDraw: function () {
      this.$redrawVueMasonry()
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  font-weight: normal;
}
.image {
  width: 100%;
  margin: 0 0 8px 0;
}
.image img {
  display: block;
  width: 100%;
}
@media screen and (min-width:768px) {
  .image {
    width: calc(100% / 3 - 20px);
    margin: 10px;
  }
}
@media screen and (min-width:1440px) {
  .image {
    width: calc(100% / 4 - 20px);
  }
}
</style>
