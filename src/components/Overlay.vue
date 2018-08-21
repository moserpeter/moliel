<template>
 <div class="overlay" v-bind:style="{opacity: opacity}">
   <slot></slot>
 </div>
</template>

<script>
export default {
  name: 'overlay',
  props: {
    opacity: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.overlay{
  position: fixed;
  height: 100%;
  width: 100%;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: black;
  z-index: 2;
}
</style>
