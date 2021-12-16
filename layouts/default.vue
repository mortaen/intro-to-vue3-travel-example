<template>
  <transition @before-enter="beforeEnter" @enter="enter" @leave="leave">
    <Nuxt />
  </transition>
</template>

<script>
import gsap from 'gsap'

export default {
  methods: {
    beforeEnter(el) {
      gsap.set(el, {
        scaleX: 0.8,
        scaleY: 1.2,
      })
    },
    enter(el, done) {
      gsap.to(el, {
        duration: 2.5,
        scaleX: 1,
        scaleY: 1,
        ease: 'expo.out',
        onComplete: done,
      })
    },
    leave(el, done) {
      gsap.to(el, {
        duration: 2.5,
        scaleX: 1,
        scaleY: 1,
        ease: 'expo.in',
        onComplete: done,
      })
    },
  },
}
</script>
