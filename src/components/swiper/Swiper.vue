<script setup>
  import { Navigation, Pagination, Scrollbar, A11y } from 'swiper';
  import { Swiper, SwiperSlide } from 'swiper/vue';

  // import 'swiper/css';
  // import 'swiper/css/navigation';
  // import 'swiper/css/pagination';
  // import 'swiper/css/scrollbar';

  import { reactive } from 'vue';

  import './style.css'

  const onSwiper = (swiper) => {
    console.log(swiper);
  };
  const onSlideChange = () => {
    console.log('slide change');
  };

  const state = reactive({
    swiperList: [
      {
        url: '/Rectangle 1740.png',
        title: 'Удивить родных',
        text: 'Встретились со знаменитостью? Веселитесь на концерте любимой группы? Отдыхаете на экзотическом пляже? Такие фото обязательно должны быть в семейном альбоме!'
      },
      {
        url: '/Rectangle 1741.png',
        title: 'Пригласить друзей на вечеринку',
        text: 'От приглашения, переданного лично в руки, настрой хорошо повеселиться обеспечен'
      },
      {
        url: '/Rectangle 1742.png',
        title: 'Прислать привет из путешествия',
        text: 'В любой точке мира — вы рядом со своими близкими.'
      },
      {
        url: '/Rectangle 1743.png',
        title: 'Подарить радость просто так!',
        text: 'Наша жизнь наполнена рутиной. Отправленная JoyKa с тёплыми словами подарит вашим близким хорошее настроение и улыбку на весь день.'
      },
      {
        url: '/Rectangle 1744.png',
        title: 'Поделиться воспоминаниями',
        text: 'Фотография с фразой: «Помнишь, как классно было?» вызовет волну положительных эмоций и желание встретиться снова.'
      },
      {
        url: '/Rectangle 1745.png',
        title: 'Удивить родных',
        text: 'Встретились со знаменитостью? Веселитесь на концерте любимой группы? Отдыхаете на экзотическом пляже? Такие фото обязательно должны быть <strong>в семейном альбоме!</strong>'
      },
      {
        url: '/Rectangle 1746.png',
        title: 'Передать привет родителям',
        text: 'Удивить друзей, порадовать родных — какая идея может быть лучше для праздника, чем JoyKa?'
      },
      {
        url: '/Rectangle 1747.png',
        title: 'Вдохновить близких своими победами',
        text: 'Забил решающий гол? Покорил очередкую вершину? Отправь JoyKa — пусть друзья разделят с тобой радость момента.'
      },
    ]
  })
</script>
<template>
  <swiper
    :modules="modules"
    :slides-per-view="3"
    :space-between="30"
    navigation
    :pagination="{ clickable: true }"
    :scrollbar="{ draggable: true }"
    @swiper="onSwiper"
    @slideChange="onSlideChange"
  >
    <swiper-slide v-for="item in state.swiperList">
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
  </swiper>
</template>