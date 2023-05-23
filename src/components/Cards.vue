<template>
  <section class="cards-section">
    <div class="container">
      <div :class="{'card-line': isCardLine}" class="card-wrap">
        <div class="card step1">
          <p class="text-static">
            Тщательно отобранный персонал
          </p>
          <p class="text-hover">
            Не нужно тратить время, силы и ресурсы на разме- щение вакансий, проведе- ние собеседований, про- верку
            кандидатов на должность уборщицы. За счет больших объемов мы можем сделать это эффективнее.
          </p>
          <div class="img-wrap">
            <img src="../assets/images/cards/card1.png">
          </div>
        </div>
        <div class="card step2">
          <p class="text-static">
            Качественная эко-химия
          </p>
          <p class="text-hover">
            Не нужно тратить время, силы и ресурсы на разме- щение вакансий, проведе- ние собеседований, про- верку
            кандидатов на должность уборщицы. За счет больших объемов мы можем сделать это эффективнее.
          </p>
          <div class="img-wrap">
            <img src="../assets/images/cards/card2.png">
          </div>
        </div>
        <div class="card step3">
          <p class="text-static">
            Контролируем качество
          </p>
          <p class="text-hover">
            Не нужно тратить время, силы и ресурсы на разме- щение вакансий, проведе- ние собеседований, про- верку
            кандидатов на должность уборщицы. За счет больших объемов мы можем сделать это эффективнее.
          </p>
          <div class="img-wrap">
            <img src="../assets/images/cards/card3.png">
          </div>
        </div>
        <div class="card step4">
          <p class="text-static">
            Работаем круглосуточно
          </p>
          <p class="text-hover">
            Не нужно тратить время, силы и ресурсы на разме- щение вакансий, проведе- ние собеседований, про- верку
            кандидатов на должность уборщицы. За счет больших объемов мы можем сделать это эффективнее.
          </p>
          <div class="img-wrap">
            <img src="../assets/images/cards/card4.png">
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {

  data() {
    return {
      isCardLine: true,
    }
  },

  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  unmounted() {
    window.removeEventListener('scroll', this.handleScroll);
  },

  methods: {
    handleScroll(e) {
      this.isCardLine = window.scrollY < 620
    },
  }
}
</script>