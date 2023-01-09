<script setup>
  import Header from '@/components/header/Header.vue'
  import Footer from '@/components/footer/Footer.vue'
  import SendButton from '@/components/sendButton/SendButton.vue'
  import Swiper from '@/components/swiper/Swiper.vue'

  import { reactive } from 'vue';

  import './App.css'

  const state = reactive({
    quizActiveQuestion: 0,
    quizQuestions: [
      {
        question: 'Выберите страну отправления',
        answer: null,
        options: [
          'Украина',
          'Грузия',
          'Тайланд',
          'Испания'
        ]
      },
      {
        question: 'Выберите город отправления',
        answer: null,
        options: [
          'Москва',
          'Сочи',
          'Воронеж',
          'Краснодар'
        ]
      },
      {
        question: 'Да?',
        answer: null,
        options: [
          'Нет',
          'Незнаю',
          'Воронеж',
          'Краснодар'
        ]
      }
    ]
  })

  const deltaPercent = 100 / state.quizQuestions.length

  const handlerNextButton = () => {
    if (state.quizActiveQuestion !== state.quizQuestions.length-1) {
      state.quizActiveQuestion++
    console.log(state.quizQuestions[state.quizActiveQuestion]);
    console.log(state.quizActiveQuestion);
    }
  }

  const handlerPrevButton = () => {
    if (state.quizActiveQuestion !== 0) {
      state.quizActiveQuestion--
    console.log(state.quizQuestions[state.quizActiveQuestion]);
    console.log(state.quizActiveQuestion);
    }
  }

  const handlerSelectAnswer = (e) => {
    
    state.quizQuestions[state.quizActiveQuestion].answer = e.target.value
    console.log(state.quizQuestions[state.quizActiveQuestion]);
    console.log(state.quizActiveQuestion);
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
      <div class="send-watch DF AIC JCSB">
        <SendButton/>
        <section class="watch DF">
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
    <h3 class="howItWorks_header">Как это работает?</h3>
    <section class="DF AIC JCSB">
      <div >
        <div class="howItWorks_item">
          <img class="howItWorks_item-img" src="/makeSelfi.png" alt="make selfi"/>
        </div>
        <div class="howItWorks_text one">
          <p class="howItWorks_strong_text">Человек делает селфи</p>
          <p class="howItWorks_light_text">Вы делаете селфи или выбираете удачное фото из галереи JoyKa</p>
        </div>
      </div>
      <div class="dots">
        <img class="dots-img" src="/dotOrange.svg" alt="dots"/>
      </div>
      <div>
        <div class="howItWorks_item">
          <img class="howItWorks_item-img" src="/craftEnvelopeGirl.png" alt="make Envelope"/>
        </div>
        <div class="howItWorks_text two">
          <p class="howItWorks_strong_text">Конверт JoyKa с ярким фото</p>
          <p class="howItWorks_light_text">Оставляете заявку на сайте или в приложении. Две минуты  и JoyKa готова!</p>
        </div>
      </div>
      <div class="dots">
        <img src="/dotBlue.svg" alt="dots"/>
      </div>
      <div>
        <div class="howItWorks_item">
          <img class="howItWorks_item-img" src="/Courier.png" alt="Courier"/>
        </div>
        <div class="howItWorks_text three">  
          <p class="howItWorks_strong_text">Курьер несёт JoyKa</p>
          <p class="howItWorks_light_text">Распечатанную фотографию в красивом конверте курьер доставит лично в руки адресату</p>
        </div>
      </div>
    </section>
    <section class="DF AIC howItWorks_happy_block">
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
          <div class="quiz_body_options_progressBar-moving" :style="{width: deltaPercent * (state.quizActiveQuestion + 1)  + '%'}"></div>
        </div>
        <div>
          <p class="quiz_body_options_title">{{ state.quizQuestions[state.quizActiveQuestion].question }}</p>
          <div class="DF JCSB">
            <label for='f' class="quiz_body_options_item_preview">
              <img class="quiz_body_options_item_preview-img" src="/Rectangle 1757.png" alt="country">
              <input class="quiz_body_options_item-check" @click="handlerSelectAnswer" id="f" name="city" value="0" type="radio" checked> 
              <p class="quiz_body_options_item-name">{{state.quizQuestions[state.quizActiveQuestion].options[0]}}</p>
            </label>
            <label for='s' class="quiz_body_options_item_preview">
              <img class="quiz_body_options_item_preview-img" src="/Rectangle 1758.png" alt="country">
              <input class="quiz_body_options_item-check" @click="handlerSelectAnswer" id="s" name="city" value="1" type="radio"> 
              <p class="quiz_body_options_item-name">{{state.quizQuestions[state.quizActiveQuestion].options[1]}}</p>
            </label>
            <label for='t' class="quiz_body_options_item_preview">
              <img class="quiz_body_options_item_preview-img" src="/Rectangle 1759.png" alt="country">
              <input class="quiz_body_options_item-check" @click="handlerSelectAnswer" id="t" name="city" value="2" type="radio"> 
              <p class="quiz_body_options_item-name">{{state.quizQuestions[state.quizActiveQuestion].options[2]}}</p>
            </label>
            <label for='fo' class="quiz_body_options_item_preview">
              <img class="quiz_body_options_item_preview-img" src="/Rectangle 1757.png" alt="country">
              <input class="quiz_body_options_item-check" @click="handlerSelectAnswer" id="fo" name="city" value="3" type="radio"> 
              <p class="quiz_body_options_item-name">{{state.quizQuestions[state.quizActiveQuestion].options[3]}}</p>
            </label>
          </div>
          <div class="DF JCSB quiz_margin_button_fix">
            <button class="quiz_body_options-prev-step" @click="handlerPrevButton">Предыдущий шаг</button>
            <button class="quiz_body_options-next-step" @click="handlerNextButton">Следующий шаг</button>
          </div>
        </div>
      </div>
    </div>
  </section>
  <Footer/>
</template>

