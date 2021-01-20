<template>
  <carousel
    :perPageCustom="[
      [480, 1],
      [768, 3],
      [576, 1],
    ]"
    :navigationEnabled="true"
    class="carousel-wrapper"
  >
    <slide v-for="item in items" :key="item.id">
      <img :src="getImgUrl(item.src)" width="200px" max-width="100%" />
    </slide>
  </carousel>
</template>

<script>
import { Carousel, Slide } from "vue-carousel";

export default {
  name: "Slick",
  components: {
    Carousel,
    Slide,
  },
  data() {
    return {
      items: [
        { src: "first.jpg", id: 1 },
        { src: "second.jpg", id: 2 },
        { src: "third.jpg", id: 3 },
        { src: "fourth.jpg", id: 4 },
        { src: "fifth.jpg", id: 5 },
        { src: "sixth.jpg", id: 6 },
      ],
    };
  },
  methods: {
    getImgUrl(pic) {
      return require(`../assets/${pic}`);
    },
  },
};
</script>

<style>
.carousel-wrapper {
  width: 90%;
  margin: auto;
}
</style>
