<template>
<vueper-slides
  class="no-shadow"
  :visible-slides="3"
  :slide-ratio="1 / 4"
  :dragging-distance="70">
  <vueper-slide v-for="i in 9" :key="i" :title="i.toString()" />
</vueper-slides>
</template>



<script>
export default {
  components: { VueperSlides, VueperSlide }
}
</script>
