<script setup>
  import { reactive } from 'vue';
  import './style.css'

  const state = reactive({
    lang: 'EN'
  })
</script>

<template>
  <header class="top_header container">
    <section class="header_body DF AIC JCSB">
      <a class="logo_header" href="#">
        <img class="logo_heade-img" src="/Logo.svg" alt="Logo" srcset=""/>
      </a>
      <nav class="header_nav">
        <ul class="DF" >
          <li class="header_nav-paragraph">
            <a class=" header_nav-paragraph-link" href="#">Как это работает</a>
          </li>
          <li class="header_nav-paragraph">
            <a class="header_nav-paragraph-link" href="#">Кто мы</a>
          </li>
          <li class="header_nav-paragraph">
            <a class="header_nav-paragraph-link" href="#">Поводы для отправки</a>
          </li>
          <li class="header_nav-paragraph">
            <a class="header_nav-paragraph-link" href="#">FAQ</a>
          </li>
          <li class="header_nav-paragraph">
            <a class="header_nav-paragraph-link" href="#">Отзывы</a>
          </li>
        </ul>
      </nav>
      <div class="lang DF">
        <p class="color_2783FE">{{state.lang}}</p>
        <div class="lang_flag">
          <img class="lang_flag-img" :src='`${state.lang == "EN" ? "/EN.svg" : "/RU.webp"}`' alt="flag" srcset=""/>
        </div>
        <div class="arrow_down"></div>
        <div class="lang_dropDown">
          <ul>
            <li class="lang_dropDown-item_ru lang_margin_fix color_2783FE" @click="state.lang = 'RU'">RU</li>
            <li class="lang_dropDown-item_en color_2783FE" @click="state.lang = 'EN'">EN</li>
          </ul>
        </div>
      </div>
    </section>
  </header>
</template>