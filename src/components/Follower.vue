<template>
  <div class="circle" ref="circle" :class="{move: moveBtn}">
    Заказать <br> уборку
  </div>
</template>

<script>
import { ref, onMounted } from 'vue'

const debounce = (func, wait) => {
  let timeout

  return function executedFunction(...args) {
    const later = () => {
      clearTimeout(timeout)
      func(...args)
    }

    clearTimeout(timeout)
    timeout = setTimeout(later, wait)
  }
}
export default {

  data() {
    return {
      moveBtn: false
    }
  },

  mounted() {
    let mousePosition = { pageX: 0, pageY: 0 }

    const init = () => {
      const circle = this.$refs?.circle
      if (!circle) return

      const offset = circle.getBoundingClientRect()
      const y = window.scrollY + window.innerHeight - offset.height - 20
      const x = window.innerWidth / 2 - offset.width / 2
      circle.style.top = `${y}px`
      circle.style.left = `${x}px`
    }
    const move = (e) => {
      mousePosition.pageX = e.pageX
      mousePosition.pageY = e.pageY

      const circle = this.$refs?.circle
      if (!circle) {
        return
      }
      const offset = circle.getBoundingClientRect()
      const x1 = window.innerWidth / 2 - 250
      const x2 = window.innerWidth / 2 + 250
      const y1 = window.scrollY + window.innerHeight - 300
      const y2 = window.scrollY + window.innerHeight - offset.height / 2


      if (e.pageX < x1 || e.pageX > x2 || e.pageY < y1 || e.pageY > y2) {
        this.moveBtn = false
        init()
        return
      }

      this.moveBtn = true
      circle.style.left = `${e.pageX - offset.width / 2}px`
      circle.style.top = `${e.pageY - offset.height / 2}px`
    }

    const scroll = (e) => {
      const k = (document.body.scrollHeight - window.scrollY) / document.body.scrollHeight
      const w = document.body.scrollHeight - window.scrollY > window.innerHeight + 195 ? k * 195 : 0
      const fs = document.body.scrollHeight - window.scrollY > window.innerHeight + 18 ? k * 18 : 0
      const circle = this.$refs?.circle

      if (!circle) {
        return
      }

      circle.style.maxWidth = `${w}px`
      circle.style.maxHeight = `${w}px`
      circle.style.fontSize = `${fs}px`

      move(mousePosition)
    }

    document.addEventListener('mousemove', move)
    window.addEventListener('scroll', scroll)

    init()
  },

}
</script>

