<template>
  <div
    class="image"
    :style="{
      'text-align': center ? 'center' : 'left'
    }"
  >
    <div
      :style="{
        'width': w,
        'height': h,
        'background': color,
        'border-radius': round ? '100%' : '3px'
      }"
    >
      <slot />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    center: Boolean,
    width: String,
    height: String,
    round: Boolean
  },
  data () {
    return {
      color: null,
      w: '100%',
      h: '200px'
    }
  },
  created () {
    this.color = this.$theme.color;
    if (this.height) { this.h = this.height }
    if (this.width) { this.w = this.width }
  }
}
</script>

<style scoped>
  .image {
    padding-top: 25px;
  }

  .image div {
    display: inline-block;
  }
</style>
