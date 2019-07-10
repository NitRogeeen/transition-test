<template>
  <div class="random-move-box">
    <my-transition
      :ox="this.ox"
      :oy="this.oy"
      :x="this.x"
      :y="this.y"
      :r="this.r"
      :s="this.s"
      :dur="this.dur"
      :easing="this.easing"
    >
      <div class="box" :style="boxStyleObject"></div>
    </my-transition>
  </div>
</template>

<script>
import MyTransition from "./MyTransition";
export default {
  name: "RandomMoveBox",
  components: {
    MyTransition
  },
  props: {
    bgColor: { type: String, default: "red" },
    height: { type: [Number, String], default: 100 },
    width: { type: [Number, String], default: 100 },
    oxMax: { type: [Number, String], default: 100 },
    oxMin: { type: [Number, String], default: 0 },
    oyMax: { type: [Number, String], default: 100 },
    oyMin: { type: [Number, String], default: 0 },
    xMax: { type: [Number, String], default: 1000 },
    xMin: { type: [Number, String], default: 0 },
    yMax: { type: [Number, String], default: 1000 },
    yMin: { type: [Number, String], default: 0 },
    sMax: { type: [Number, String], default: 2 },
    sMin: { type: [Number, String], default: 0.5 },
    rMax: { type: [Number, String], default: 720 },
    rMin: { type: [Number, String], default: 0 },
    durMax: { type: [Number, String], default: 1500 },
    durMin: { type: [Number, String], default: 500 },
    opacity: { type: [Number, String], default: 1 }
  },
  data() {
    return {
      ox: 0,
      oy: 0,
      x: 0,
      y: 0,
      s: 1,
      r: 0,
      dur: 1000,
      easing: "ease"
    };
  },
  mounted: function() {
    this.randMove();
  },
  computed: {
    boxStyleObject: function() {
      return {
        backgroundColor: this.bgColor,
        height: `${this.height}px`,
        width: `${this.width}px`,
        opacity: this.opacity
      };
    }
  },
  methods: {
    randMovePart() {
      return new Promise((resolve, reject) => {
        this.ox = ~~(
          Math.random() * (this.oxMax + 1 - this.oxMin) +
          this.oxMin
        );
        this.oy = ~~(
          Math.random() * (this.oyMax + 1 - this.oyMin) +
          this.oyMin
        );
        this.x = ~~(Math.random() * (this.xMax + 1 - this.xMin) + this.xMin);
        this.y = ~~(Math.random() * (this.yMax + 1 - this.yMin) + this.yMin);
        this.s = Math.random() * (this.sMax - this.sMin) + this.sMin;
        this.r = ~~(Math.random() * (this.rMax + 1 - this.rMin) + this.rMin);
        this.dur = ~~(
          Math.random() * (this.durMax + 1 - this.durMin) +
          this.durMin
        );
        setTimeout(() => resolve(), this.dur);
      });
    },
    async randMove() {
      while (true) {
        await this.randMovePart();
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
