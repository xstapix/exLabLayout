<script setup>
  import Header from '@/components/header/Header.vue'
  import Footer from '@/components/footer/Footer.vue'
  import SendButton from '@/components/sendButton/SendButton.vue'
  import Swiper from '@/components/swiper/Swiper.vue'

  import { reactive } from 'vue';

  import './App.css'
  import './media_App.css'

  const state = reactive({
    quizActiveQuestion: 0,
    quizQuestions: [
      {
        question: 'Выберите страну отправления',
        answer: null,
        options: [
          {
            name: 'Украина',
            id: 'uk',
            value: 0,
            selected: true
          },
          {
            name: 'Россия',
            id: 'ru',
            value: 1,
            selected: false
          },
          {
            name: 'Испания',
            id: 'spa',
            value: 2,
            selected: false
          },
          {
            name: 'Тайланд',
            id: 'tad',
            value: 3,
            selected: false
          }
        ]
      },
      {
        question: 'Выберите город отправления',
        answer: null,
        options: [
          {
            name: 'Москва',
            id: 'msk',
            value: 0,
            selected: true
          },
          {
            name: 'Сочи',
            id: 'sch',
            value: 1,
            selected: false
          },
          {
            name: 'Воронеж',
            id: 'vrn',
            value: 2,
            selected: false
          },
          {
            name: 'Краснодар',
            id: 'kdr',
            value: 3,
            selected: false
          }
        ]
      },
      {
        question: 'Да?',
        answer: null,
        options: [
          {
            name: 'Да',
            id: 'yes',
            value: 0,
            selected: true
          },
          {
            name: 'Нет',
            id: 'no',
            value: 1,
            selected: false
          },
          {
            name: 'Может',
            id: 'mb',
            value: 2,
            selected: false
          },
          {
            name: 'Не знаю',
            id: 'dkn',
            value: 3
          }
        ]
      }
    ]
  })

  const deltaPercent = 100 / state.quizQuestions.length

  const handlerNextButton = () => {
    if (state.quizActiveQuestion !== state.quizQuestions.length-1) {
      state.quizActiveQuestion++
    }
  }

  const handlerPrevButton = () => {
    if (state.quizActiveQuestion !== 0) {
      state.quizActiveQuestion--
    }
  }

  const handlerSelectAnswer = (e) => {
    state.quizQuestions[state.quizActiveQuestion].answer = e.target.value

    for (let item in state.quizQuestions[state.quizActiveQuestion].options) {
      state.quizQuestions[state.quizActiveQuestion].options[item].selected = false
    }

    state.quizQuestions[state.quizActiveQuestion].options[e.target.value].selected = true
  }

</script>

<template>
  <Header/>
  <section class="helloMain">
    <div class="background"></div>
    <section class="helloBlock container">
      <h1 class="hello_text">JoyKa — эмоции в конверте Дари моменты радости вместе с JoyMail!</h1>
      <ul>
        <li class="DF AIC hello_checkMark_paragraph">
          Доставка из любой точки мира
        </li>
        <li class="DF AIC hello_checkMark_paragraph">
          За 12 часов
        </li>
        <li class="DF AIC hello_checkMark_paragraph">
          Лично в руки адресату
        </li>
      </ul>
      <div class="send-watch DF DB AIC JCSB">
        <SendButton/>
        <section class="watch DF JCC">
          <div class="watch_play">
            <img class="watch_play_img" src="/play.svg" alt="play" srcset="">
          </div>
          <div class="watch_text ">
            <p class="watch_text_pharagraph">Посмотрите видеообзор нашего подарка</p>
            <p class="watch_text_second-pharagraph">Время просмотра 1:23 сек</p>
          </div>
        </section>
      </div>
    </section>
  </section>
  <section class="howItWorks container">
    <h2 class="howItWorks_header">Как это работает?</h2>
    <section class="DF DB JCSB">
      <div class="howItWorks_item">
        <div class="howItWorks_item-img_body">
          <img class="howItWorks_item-img-first" src="/makeSelfi.png" alt="make selfi"/>
        </div>
        <div class="howItWorks_text one">
          <p class="howItWorks_strong_text">Человек делает селфи</p>
          <p class="howItWorks_light_text">Вы делаете селфи или выбираете удачное фото из галереи JoyKa</p>
        </div>
      </div>
      <div class="dots DF JCC">
        <picture>
          <source class="dots-img" 
            srcset="/dotOrange.svg"
            media="(min-width: 428px)">
          <img  class="dots-img" src="/dots_orange-modil.svg" alt="dots">
        </picture>
      </div>
      <div class="howItWorks_item">
        <div class="howItWorks_item-img_body">
          <img class="howItWorks_item-img-two" src="/craftEnvelopeGirl.png" alt="make Envelope"/>
        </div>
        <div class="howItWorks_text two">
          <p class="howItWorks_strong_text">Конверт JoyKa с ярким фото</p>
          <p class="howItWorks_light_text">Оставляете заявку на сайте или в приложении. Две минуты  и JoyKa готова!</p>
        </div>
      </div>
      <div class="dots DF JCC">
        <picture>
          <source class="dots-img" 
            srcset="/dotBlue.svg"
            media="(min-width: 428px)">
          <img class="dots-img" src="/dots_blue-mobil.svg" alt="dots">
        </picture>
      </div>
      <div class="howItWorks_item">
        <div class="howItWorks_item-img_body">
          <img class="howItWorks_item-img-three" src="/Courier.png" alt="Courier"/>
        </div>
        <div class="howItWorks_text three">  
          <p class="howItWorks_strong_text">Курьер несёт JoyKa</p>
          <p class="howItWorks_light_text">Распечатанную фотографию в красивом конверте курьер доставит лично в руки адресату</p>
        </div>
      </div>
    </section>
    <div class="dots_additional JCC">
      <picture>
        <source class="dots-img" 
          srcset="/dotOrange.svg"
          media="(min-width: 428px)">
        <img  class="dots-img" src="/dots_orange-modil.svg" alt="dots">
      </picture>
    </div>
    <section class="DF DB AIC howItWorks_happy_block">
      <div class="howItWorks_happy-body">
        <div class="howItWorks_happy-gradient"></div>
        <div class="howItWorks_happy-img"></div>
      </div>
      <div class="howItWorks_happy_content four">
        <p class="howItWorks_happy_text-strong">
          Адресат радуется полученной JoyKa
        </p>
        <p class="howItWorks_happy_text-light">
          Ваше фото с личным посланием подарят близким хорошее настроение на весь день
        </p>
        <SendButton/>
      </div>
    </section>
  </section>
  <section>
    <div class="occasionsToSend-background"></div>
    <section class="occasionsToSend-content ">
      <p class="occasionsToSend-content_header">Поводы для отправки</p>
      <Swiper/>
    </section>
  </section>
  <section class="quiz">
    <div class="quiz_body DF AIC">
      <div class="quiz_body_girl">
        <img class="quiz_body_girl-img" src="/quizGirl.png" alt="">
      </div>
      <div class="quiz_body_options">
        <p class="quiz_body_options-steps">Шаг {{ state.quizActiveQuestion + 1 }} из {{ state.quizQuestions.length }}</p>
        <div class="quiz_body_options_progressBar">
          <div 
            class="quiz_body_options_progressBar-moving" 
            :style="{width: deltaPercent * (state.quizActiveQuestion + 1)  + '%'}"></div>
        </div>
        <div>
          <p class="quiz_body_options_title">{{ state.quizQuestions[state.quizActiveQuestion].question }}</p>
          <div class="DF JCC FWW quiz_body_options-margin-fix">
            <label 
              v-for="item in state.quizQuestions[state.quizActiveQuestion].options" 
              :for='item.id' 
              class="quiz_body_options_item_preview quiz_body_options_item_preview-margin_fix">
              <img 
                class="quiz_body_options_item_preview-img" 
                src="/Rectangle 1757.png" alt="country">
              <input 
                class="quiz_body_options_item-check" 
                @click="handlerSelectAnswer" 
                :id='item.id' name="city" :value='item.value' type="radio" 
                :checked='item.selected'> 
              <p class="quiz_body_options_item-name">{{item.name}}</p>
            </label>
          </div>
          <div class="DF DB JCSB quiz_margin_button_fix">
            <button class="quiz_body_options-prev-step DF JCC" @click="handlerPrevButton">Предыдущий шаг</button>
            <button class="quiz_body_options-next-step DF JCC" @click="handlerNextButton">Следующий шаг</button>
          </div>
        </div>
      </div>
    </div>
  </section>
  <Footer/>
</template>

