<template>
  <section class="how-clean">
    <div class="clean-wrapper" ref="root">
      <div class="container">
        <div class="clean-wrap">
          <div class="title">
            <h2>
              Как мы убираем
            </h2>
            <p>
              Клинер приезжает в назначенное время со всем необходимым и сразу приступает к делу. Вам остаётся только
              оценить результат.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section class="clean-animation" :class="{'open-menu': openMenu}">
    <div class="menu">
      <h4>Как мы убираем</h4>
      <ul class="categories">
        <li class="text" v-for="(s, index) in menu"
            :class="{ 'active': activeIndex === index }" :key="s.id"
            @click="onClickMenu(s, index)">
          {{ s.name }}
        </li>
      </ul>
    </div>

    <div class="slider-wrapper" ref="clean">
      <slider :height="80" :items="items" :active-slide="activeSlide"/>
      <div class="block-pluses first" v-show="activeSlide===0" :class="{'slider-ready': isReady}">
       <plus text="Чистим фасад вытяжки" class="one" />
        <plus text="Чистим фасад вытяжки" class="two" />
        <plus text="Чистим фасад вытяжки" class="three" />
        <plus text="Чистим фасад вытяжки" class="four" />
        <plus text="Чистим фасад вытяжки" class="five" />
        <plus text="Чистим фасад вытяжки" class="six" />
        <plus text="Чистим фасад вытяжки" class="seven" />
      </div>

      <div class="block-pluses second" v-show="activeSlide===1" :class="{'slider-ready': isReady}">
        <plus text="Чистим фасад вытяжки" class="one" />
        <plus text="Чистим фасад вытяжки" class="two" />
        <plus text="Чистим фасад вытяжки" class="three" />
        <plus text="Чистим фасад вытяжки" class="four" />
        <plus text="Чистим фасад вытяжки" class="five" />
      </div>

      <div class="block-pluses third" v-show="activeSlide===2" :class="{'slider-ready': isReady}">
        <plus text="Чистим фасад вытяжки" class="eight" />
        <plus text="Чистим фасад вытяжки" class="nine" />
        <plus text="Чистим фасад вытяжки" class="ten" />
        <plus text="Чистим фасад вытяжки" class="eleven" />
        <plus text="Чистим фасад вытяжки" class="twelve" />
      </div>
    </div>
  </section>
</template>

<script>
import Slider from '@/components/Slider.vue'
import Plus from "@/components/Plus.vue";

export default {
  components: {
    Slider,
    Plus
  },

  data() {
    return {
      menu: [
        {id: 1, name: 'Кухня'},
        {id: 2, name: 'Комнаты'},
        {id: 3, name: 'Ванная'},
        {id: 4, name: 'Прихожая'},
      ],
      items: [
        'kitchen.png',
        'kitchen.png',
        'bathroom.png',
        'bathroom.png',
      ],
      activeSlide: 0,
      openMenu: false,
      activeIndex: 0,
      show: false,
      isReady: true
    }
  },
  mounted() {
    window.addEventListener('scroll', this.onScroll)
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.onScroll)
  },

  computed: {
    btnText: function() {
      if(this.show) {
        return  'Скрыть'
      }
      return 'Текст'
    }
  },

  methods: {
    onScroll() {
      if (window.scrollY - 200 > this.$refs.clean.offsetTop) {
        this.openMenu = true
      }
    },

    onClickMenu(s, index) {
      setTimeout(() => this.activeIndex = index, 500)
      this.activeSlide = index
      this.isReady = false
      setTimeout(() => this.isReady = true, 500)
    }
  }

}
</script>
