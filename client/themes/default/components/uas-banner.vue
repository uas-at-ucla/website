<template>
  <v-carousel
    hide-delimiters
    interval="3000"
    width="100%"
    height="65vh" >
    <v-carousel-item src="/img/front_page_carousel/squad.jpg" />
    <v-carousel-item src="/img/front_page_carousel/auvsi_group_photo.jpg" />
    <v-carousel-item src="/img/front_page_carousel/spinny_grad_photo.jpg" />
    <v-carousel-item src="/img/front_page_carousel/rc_controller.jpg" />
    <v-carousel-item src="/img/front_page_carousel/spinny_flying.jpg" />
    <v-carousel-item src="/img/front_page_carousel/prop_closeup.jpg" />
    <v-carousel-item src="/img/front_page_carousel/software_workshop.jpg" />
    <v-carousel-item src="/img/front_page_carousel/sony_camera.jpg" />
    <v-carousel-item src="/img/front_page_carousel/flappy.jpg" />
    <v-carousel-item src="/img/front_page_carousel/spinny_portrait.jpg" />
    <v-carousel-item src="/img/front_page_carousel/mathz.jpg" />
    <v-carousel-item src="/img/front_page_carousel/we_make_spinny.jpg" />
    <v-carousel-item src="/img/front_page_carousel/spinny_render.jpg" />
    <v-carousel-item src="/img/front_page_carousel/veritasium1.jpg" />
    <v-carousel-item src="/img/front_page_carousel/veritasium2.jpg" />
    <v-carousel-item src="/img/front_page_carousel/2016_auvsi.jpg" />
  </v-carousel>
</template>

<script>
export default {
  data() {
    return {
      slide: 0,
      sliding: null
    }
  },
  methods: {
    onSlideStart(slide) {
      this.sliding = true
    },
    onSlideEnd(slide) {
      this.sliding = false
    }
  }
}
</script>

<style>

</style>
