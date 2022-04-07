<template>
  <button class="btn-subtract btn" @click="$emit('onClick')" :style="cssVars">
    <slot />
  </button>
</template>

<script>
export default {
  props: ['color', 'backgroundColor', 'fontWeight', 'width'],
  computed: {
    cssVars() {
      return {
         '--color':this.color, 
         '--width' :this.width,
         '--background':this.backgroundColor,
         '--fontWeight' : this.fontWeight
      }
    },
  },
}
</script>

<style scoped>
button{
    color: var(--color);
    width: var(--width);
    background: var(--background);
    font-weight: var(--fontWeight);
}

</style>>
