<script setup>
  import Header from '@/components/header/Header.vue'
  import Footer from '@/components/footer/Footer.vue'
  import SendButton from '@/components/sendButton/SendButton.vue'

  import './App.css'
</script>

<template>
  <Header/>
  <section class="container">
    <div class="background"></div>
    <div class="cloud"></div>
    <img class="girl_img" alt="girl" src="/girl.svg"/>
    <img class="prise" alt="prise" src="/craftEnvelope.svg"/>
    <img class="prise2" alt="prise" src="/craftEnvelope2.svg"/>
    <img class="balloon" alt="balloon" src="/balloon.svg"/>
    <section class="helloBlock">
      <h1 class="hello_text">JoyKa — эмоции в конверте Дари моменты радости вместе с JoyMail!</h1>
      <ul>
        <li class="DF AIC hello_checkMark_paragraph">
          <div>
            <img src="/coolicon.svg" alt="check mark"/>
          </div>
          <p class="hello_checkMark _text">Доставка из любой точки мира</p>
        </li>
        <li class="DF AIC hello_checkMark_paragraph">
          <div>
            <img src="/coolicon.svg" alt="check mark"/>
          </div>
          <p class="hello_checkMark _text">За 12 часов</p>
        </li>
        <li class="DF AIC hello_checkMark_paragraph">
          <div>
            <img src="/coolicon.svg" alt="check mark"/>
          </div>
          <p class="hello_checkMark _text">Лично в руки адресату</p>
        </li>
      </ul>
      <div class="send-watch">
        <SendButton/>
        <section class="watch">
          <div class="watch_play">
            <img class="watch_play_img" src="/play.svg" alt="play" srcset="">
            <div class="circle_small"></div>
            <div class="circle_big"></div>
          </div>
          <div class="watch_text ">
            <p class="watch_text_pharagraph">Посмотрите видеообзор нашего подарка</p>
            <p class="watch_text_second-pharagraph">Время просмотра1:23 сек</p>
          </div>
          <div class="white_shadow"></div>
        </section>
      </div>
    </section>
  </section>
  <section class="howItWorks">
    <h3 class="howItWorks_header">Как это работает?</h3>
    <section class="DF AIC JCSB">
      <div>
        <img src="/makeSelfi.png" alt="make selfi"/>
        <p class="howItWorks_strong_text">Человек<br/> делает селфи</p>
        <p class="howItWorks_light_text">Вы делаете селфи <br/> или выбираете удачное фото<br/> из галереи JoyKa</p>
      </div>
      <div>
        <img src="/craftEnvelope.png" alt="make Envelope"/>
        <p class="howItWorks_strong_text">Конверт JoyKa<br/> с ярким фото</p>
        <p class="howItWorks_light_text">Оставляете заявку на сайте<br/> или в приложении. Две минуты <br/> и JoyKa готова!</p>
      </div>
      <div>
        <img src="/Courier.png" alt="Courier"/>
        <p class="howItWorks_strong_text">Курьер<br/> несёт JoyKa</p>
        <p class="howItWorks_light_text">Распечатанную фотографию<br/> в красивом конверте курьер<br/> доставит лично в руки адресату</p>
      </div>
    </section>
  </section>
  <Footer/>
</template>

<style scoped>
</style>

