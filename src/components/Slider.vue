<template>
  <div class="slider" :style="{'padding-bottom': `${height}%`}">
    <div class="slider-inner" :style="{'width': `${100*items.length}%`, 'left': `${-100*activeSlide}%`}">
      <div
          v-for="(item, ind) in items"
          :key="ind"
          class="slide"
          :style="{'background-image': `url(${item})`, 'width': `${100/items.length}%`}"
      ></div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    items: { type: Array, required: true },
    height: { type: Number, default: 58},
    activeSlide: {type: Number, default: 0}
  }
}
</script>

<style lang="scss" scoped>

.slider {
  overflow: hidden;
  position: relative;
  width: 100%;
  height: 0;
}

.slider-inner {
  position: absolute;
  left: 0;
  top: 0;
  height: 100%;
  transition: left 2s;
}

.slide {
  display: inline-block;
  position: relative;
  height: 100%;
  background-attachment: fixed;
  background-position: center center;
  background-size: cover;
  background-repeat: no-repeat;
}
</style>
