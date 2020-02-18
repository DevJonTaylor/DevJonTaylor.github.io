<template>
  <q-page class="flex flex-center">
    <img ref="logo" alt="Quasar logo" src="~assets/quasar-logo-full.svg">
  </q-page>
</template>

<script>
import { TimelineLite, Back } from 'gsap';

export default {
  name: 'PageIndex',
  mounted() {
    const { logo } = this.$refs;
    const timeLine = new TimelineLite();

    timeLine
    .to(logo, 3, {
      x: 200,
      rotation: 90,
      ease: Back.easeInOut
    })
    .to(logo, 3, {
      x: 0,
      rotation: 0,
      ease: Back.easeInOut
    })
  }
}
</script>
