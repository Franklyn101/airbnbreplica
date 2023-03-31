<template>
    <div>
      <transition-group name="fade" tag="div">
        <div v-for="i in [currentIndex]" :key="i" >
          <img class="imgslide" :src="currentImg" />
        </div>
      </transition-group>
      <button class="nextbtn"><a class="prev" @click="prev" href="#">&#10094; </a></button>
      <button class="prevbtn"><a class="next" @click="next" href="#">&#10093; </a></button>
    </div>
  </template>
  <script>
  export default {
    name: "Slider",
    data() {
      return {
        images: [
        "pool1.webp",
        "pool2.webp",
        "pool3.webp",
        "pool4.webp",
        "pool5.webp",
        
        
        ],
        timer: null,
        currentIndex: 0
      };
    },
  
    mounted: function() {
      this.startSlide();
    },
  
    methods: {
    //   startSlide: function() {
    //     this.timer = setInterval(this.next, 4000);
    //   },
  
      next: function() {
        this.currentIndex += 1;
      },
      prev: function() {
        this.currentIndex -= 1;
      }
    },
  
    computed: {
      currentImg: function() {
        return this.images[Math.abs(this.currentIndex) % this.images.length];
      }
    }
  };
  
  
  </script>