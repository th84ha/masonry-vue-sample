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
        require('@/assets/01.jpg'),
        require('@/assets/02.jpg'),
        require('@/assets/03.jpg'),
        require('@/assets/04.jpg'),
        require('@/assets/05.jpg'),
        require('@/assets/06.jpg'),
        require('@/assets/07.jpg'),
        require('@/assets/08.jpg'),
        require('@/assets/09.jpg'),
        require('@/assets/10.jpg'),
        require('@/assets/11.jpg'),
        require('@/assets/12.jpg'),
        require('@/assets/13.jpg'),
        require('@/assets/14.jpg'),
        require('@/assets/15.jpg')
      ]
    }
  },
  mounted: function () {
    this.$redrawVueMasonry()
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
