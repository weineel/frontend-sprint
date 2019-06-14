<template>
  <div class="scroll2-dom">
    <button @click="scroll2anchor"> scroll to anchor </button>
    <div v-for="i in 100" :key="i"> placehold </div>
    <div ref="anchor"> anchor </div>
    <div v-for="i in 100" :key="i + 100"> placehold </div>
  </div>
</template>

<script>
// 获取窗口
let windowElement = null
// eslint-disable-next-line no-cond-assign
windowElement = ((windowElement = document.documentElement) || (windowElement = document.body.parentNode)) && typeof windowElement.scrollLeft === 'number' ? windowElement : document.body

function getElementTop(element) {
  let actualTop = element.offsetTop
  let current = element.offsetParent
  while (current !== null) {
    actualTop += current.offsetTop
    current = current.offsetParent
  }
  return actualTop
}

export default {
  name: 'Scroll2Dom',

  components: {},

  props: {},

  data() {
    return {}
  },

  computed: {},

  watch: {},

  // mounted() {
    // this.init()
  // },

  methods: {
    // init() {
    // },
    scroll2anchor() {
      windowElement.scrollTop = getElementTop(this.$refs.anchor)
    }
  }
}
</script>

<style lang="stylus">
// @import "../../assets/css/variable"
// .scroll2-dom
  // background-color $white
</style>
