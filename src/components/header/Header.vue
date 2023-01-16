<script setup>
  import { reactive } from 'vue';
  import './style.css'
  import './media_style.css'

  const state = reactive({
    lang: 'EN',
    activeLang: false,
    menuActive: false
  })

  const handlerLang = () => {
    state.activeLang = !state.activeLang
  }

  const handlerMenu = () => {
    state.menuActive = !state.menuActive
    
    if (state.menuActive) {
      document.body.style.overflow = 'hidden'
    } else {
      document.body.style.overflow = 'visible'
    }
  }
</script>

<template>
  <header class="top_header container">
    <section class="header_body DF AIC JCSB">
      <a class="logo_header" href="/">
        <img class="logo_header-img" src="/Logo.svg" alt="Logo" srcset=""/>
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
      <div class="lang DF" @click="handlerLang">
        <p class="color_2783FE">{{state.lang}}</p>
        <div class="lang_flag">
          <img class="lang_flag-img" :src='`/${state.lang}.svg`' alt="flag" srcset=""/>
        </div>
        <div class="arrow_down"></div>
        <div :class="state.activeLang ? 'lang_dropDown-active' : 'lang_dropDown-none'">
          <ul>
            <li class="lang_dropDown-item_ru lang_margin_fix color_2783FE" @click="state.lang = 'AF'">AF</li>
            <li class="lang_dropDown-item_en color_2783FE" @click="state.lang = 'EN'">EN</li>
          </ul>
        </div>
      </div>
      <div class="header_nav-modil_menu" @click="handlerMenu">
        <img class="header_nav-modil_menu-img" src="/menu.svg" alt="" srcset="">
      </div>
      <nav :class="state.menuActive ? 'header_nav-modil' : 'DN'">
        <div class="header_nav-modil_close DF JCE" @click="handlerMenu">
          <img class="header_nav-modil_close-img" src="/close.svg" alt="" srcset="">
        </div>
        <ul class="DB" >
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
    </section>
  </header>
</template>