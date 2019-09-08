<template>
  <div id="app">
    <span class="text">{{test }}</span>
    <router-view/>
  </div>
</template>
<script>
import { mapGetters } from 'vuex'
const getters = {
  test () {
    return 1
  }
}
function fn (arr) {
  let date = {}
  arr.forEach(key => {
    if (getters.hasOwnProperty(key)) { date[key] = getters[key] }
  })

  return date
}
export default {
  mounted () {
    console.log(this.test)
  },
  computed: {
    ...mapGetters(['test']),
    ...fn(['test'])
  }
}
document.addEventListener('DOMCont entLoaded', () => {
  const html = document.querySelector('html')
  let fontSize = window.innerWidth / 10
  fontSize = fontSize > 50 ? 50 : fontSize
  html.style.fontSize = fontSize + 'px'
})
</script>

<style lang="scss" scoped>
  @import "../src/assets/styles/global";
.text{
font-family: "Days One";
font-size: px2rem(20);
color: orange;
}

</style>
