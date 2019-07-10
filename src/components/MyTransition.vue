<template>
  <div class="my-transition" :style="styleObject">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "MyTransition",
  props: {
    ox: { type: [String, Number], default: 0 },
    oy: { type: [String, Number], default: 0 },
    x: { type: [String, Number], default: 0 },
    y: { type: [String, Number], default: 0 },
    s: { type: [String, Number], default: 1 },
    r: { type: [String, Number], default: 0 },
    dur: { type: [String, Number], default: 0 },
    easing: { type: String, default: "linear" }
  },
  computed: {
    styleObject: function() {
      return {
        transformOrigin: `${this.ox}px ${this.oy}px`,
        transform: `translate(${this.x}px, ${this.y}px)
          scale(${this.s})
          rotate(${this.r}deg)`,
        transition: `transform-origin ${this.dur}ms ${this.easing},
          transform ${this.dur}ms ${this.easing}`
      };
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.my-transition {
  position: absolute;
  top: 0;
  left: 0;
}
</style>
