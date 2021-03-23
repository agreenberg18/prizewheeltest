<template>
  <canvas id="canvas" width="1000" height="600">
    Canvas not supported, use another browser.
  </canvas>
  <button @click="startAnimation">Spin the wheel</button>
</template>

<script>
import TweenMax from "@/assets/TweenMax.min.js";
import Winwheel from "winwheel/lib/Winwheel.js";
export default {
  data() {
    return {
      theWheel: null,
    };
  },
  mounted() {
    this.theWheel = new Winwheel({
      numSegments: 4,
      outerRadius: 170,
      segments: [
        { fillStyle: "#eae56f", text: "Prize One" },
        { fillStyle: "#89f26e", text: "Prize Two" },
        { fillStyle: "#7de6ef", text: "Prize Three" },
        { fillStyle: "#e7706f", text: "Prize Four" },
      ],
      // Note animation properties passed in constructor parameters.
      animation: {
        type: "spinToStop", // Type of animation.
        duration: 5, // How long the animation is to take in seconds.
        spins: 8,
        "callbackFinished": this.alertPrize
      },
    });
  },
  methods: {
    startAnimation() {
      this.theWheel.startAnimation();
    },
    alertPrize(){
      alert('hello')
      console.log('testing')
    }
  },
};
</script>

<style>
</style>