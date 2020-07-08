<template>
  <q-carousel
    v-model="selectedSlide"
    transition-prev="scale"
    transition-next="scale"
    swipeable
    animated
    control-color="white"
    navigation
    padding
    height="350px"
    @input="currentSlide()"
    class="bg-primary text-white shadow-1 rounded-borders"
  >
    <q-carousel-slide
      v-for="slide in slides"
      :key="slide.id"
      :name="slide.id"
      class="column no-wrap flex-center"
    >
      <q-icon
        :name="slide.icon"
        size="125px"
        color="white"
      />
      <div class="custom-caption">
        <div class="text-h2">{{ slide.title }}</div>
        <div class="q-pa-sm text-subtitle1">{{ slide.caption }}</div>
      </div>
      <q-btn/>
    </q-carousel-slide>
  </q-carousel>
</template>

<script>
export default {
  data () {
    return {
      selectedSlide: 1,
      slides: [
        {
          id: 1,
          title: 'Projects',
          caption: 'Stuff I work on',
          icon: 'code'
        },
        {
          id: 2,
          title: 'Blog',
          caption: 'Stuff I write about',
          icon: 'library_books'
        },
        {
          id: 3,
          title: 'Resume',
          caption: 'All my stuff',
          icon: 'work_outline'
        }
      ]
    }
  },
  methods: {
    currentSlide () {
      var page = this.slides.find(slide => slide.id === this.selectedSlide).title
      var path = '/' + page
      if (this.$route.path !== path) this.$router.push(path)
    }
  }
}
</script>

<style lang="scss" scoped>
.custom-caption {
  text-align: center;
  padding: 12px;
  color: white;
}
</style>
