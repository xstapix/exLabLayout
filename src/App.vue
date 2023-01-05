<script setup>
  import Header from '@/components/header/Header.vue'
  import Footer from '@/components/footer/Footer.vue'
  import SendButton from '@/components/sendButton/SendButton.vue'

  import './App.css'
</script>

<template>
  <Header/>
  <section class="helloMain">
    <div class="background"></div>
    <section class="helloBlock container">
      <h1 class="hello_text">JoyKa — эмоции в конверте Дари моменты радости вместе с JoyMail!</h1>
      <ul>
        <li class="DF AIC hello_checkMark_paragraph">
          <div class="checkMark">
            <img class="checkMark-img" src="/coolicon.svg" alt="check mark"/>
          </div>
          Доставка из любой точки мира
        </li>
        <li class="DF AIC hello_checkMark_paragraph">
          <div class="checkMark">
            <img class="checkMark-img" src="/coolicon.svg" alt="check mark"/>
          </div>
          За 12 часов
        </li>
        <li class="DF AIC hello_checkMark_paragraph">
          <div class="checkMark">
            <img class="checkMark-img" src="/coolicon.svg" alt="check mark"/>
          </div>
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
            <p class="watch_text_second-pharagraph">Время просмотра1:23 сек</p>
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
        <div class="howItWorks_text">

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
        <div class="howItWorks_text">
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
        <div class="howItWorks_text">  
          <p class="howItWorks_strong_text">Курьер несёт JoyKa</p>
          <p class="howItWorks_light_text">Распечатанную фотографию в красивом конверте курьер доставит лично в руки адресату</p>
        </div>
      </div>
    </section>
  </section>
  <Footer/>
</template>

<style scoped>
</style>

