<script setup>
  import { Navigation, Pagination, A11y } from 'swiper';
  import { Swiper, SwiperSlide } from 'swiper/vue';

  import { reactive } from 'vue';

  import './style.css'

  const state = reactive({
    swiperList: [
      {
        id: 1,
        url: '/Rectangle 1740.png',
        title: 'Удивить родных',
        text: 'Встретились со знаменитостью? Веселитесь на концерте любимой группы? Отдыхаете на экзотическом пляже? Такие фото обязательно должны быть в семейном альбоме!'
      },
      { 
        id: 2,
        url: '/Rectangle 1741.png',
        title: 'Пригласить друзей на вечеринку',
        text: 'От приглашения, переданного лично в руки, настрой хорошо повеселиться обеспечен'
      },
      {
        id: 3,
        url: '/Rectangle 1742.png',
        title: 'Прислать привет из путешествия',
        text: 'В любой точке мира — вы рядом со своими близкими.'
      },
      {
        id: 4,
        url: '/Rectangle 1743.png',
        title: 'Подарить радость просто так!',
        text: 'Наша жизнь наполнена рутиной. Отправленная JoyKa с тёплыми словами подарит вашим близким хорошее настроение и улыбку на весь день.'
      },
      {
        id: 5,
        url: '/Rectangle 1744.png',
        title: 'Поделиться воспоминаниями',
        text: 'Фотография с фразой: «Помнишь, как классно было?» вызовет волну положительных эмоций и желание встретиться снова.'
      },
      {
        id: 6,
        url: '/Rectangle 1745.png',
        title: 'Удивить родных',
        text: 'Встретились со знаменитостью? Веселитесь на концерте любимой группы? Отдыхаете на экзотическом пляже? Такие фото обязательно должны быть <strong>в семейном альбоме!</strong>'
      },
      {
        id: 7,
        url: '/Rectangle 1746.png',
        title: 'Передать привет родителям',
        text: 'Удивить друзей, порадовать родных — какая идея может быть лучше для праздника, чем JoyKa?'
      },
      {
        id: 8,
        url: '/Rectangle 1747.png',
        title: 'Вдохновить близких своими победами',
        text: 'Забил решающий гол? Покорил очередкую вершину? Отправь JoyKa — пусть друзья разделят с тобой радость момента.'
      },
    ],
    sliderCounter: 1
  })

  const handlerPrev = () => {
    if (state.sliderCounter != 1) {
      state.sliderCounter--
    }
  }

  const handlerNext = () => {
    if (state.sliderCounter != 8) {
      state.sliderCounter++
    }
  }
  
</script>
<template>
  <swiper
    :modules="[Navigation, Pagination, A11y]"
    :slides-per-view="3"
    :space-between="30"
    :navigation="{ nextEl: '.nextArrow', prevEl: '.prevArrow', hideOnClick: true,}"
    :pagination="{ type: 'fraction' }"
    :scrollbar="{ draggable: true }"
    @swiper="onSwiper"
    @slideChange="onSlideChange"
  >
    <swiper-slide v-for="item in state.swiperList" :id="item.id" key="{{ item.id }}">
      <section class="swiper_item">
        <div class="swiper_item-body">
          <div class="swiper_item_img-body">
            <img class="swiper_item_img" :src="`${item.url}`" alt="" srcset="">
          </div>
          <div class="swiper_item_text">
            <p class="swiper_item_text-strong">{{ item.title }}</p>
            <p class="swiper_item_text-light">{{ item.text }}</p>
          </div>
        </div>
      </section>
    </swiper-slide>
    <div class="swiper_navigation DF AIC">
      <div class="DF">
        <div class="swiper_navigation_arrows-body">
          <div class="prevArrow"></div>
        </div>
        <div class="swiper_navigation_arrows-body" >
          <div class="nextArrow"></div>
        </div>
      </div>
      <p class="swiper_navigation_text-light">Листайте дальше</p>
      <!-- <p class="swiper_navigation_counter"><span>0{{ state.sliderCounter }}</span>/08</p> -->
    </div>
  </swiper>
</template>