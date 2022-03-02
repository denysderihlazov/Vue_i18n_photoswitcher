<template>
    <div>
        <nav class="navbar navbar-light bg-dark">
            <a class="navbar-brand" href="#">
                Vue i18n library
            </a>
            <select v-model="$i18n.locale" class="mb-7 navbar-item has-text-white is-align-self-center">
                <option v-for="(lang, i) in langs" :key="`Lang${i}`" :value="lang">{{ lang }} </option>
            </select>
        </nav>
        <h3 class="light_mode_text">{{ $t('text') }}</h3>
        <img :src="imgSort[$i18n.locale]" alt="">
    </div>
</template>

<script>
import img_en from './assets/en.png'
import img_pl from './assets/pl.png'
import img_ru from './assets/ru.png'

export default {
    name: 'App',
    data(){
        return {
            langs: ['en', 'pl', 'ru'],
            globalInjection: true,
            showMobileMenu: false,
            cart: {
                items: []
            },
            imgSort: {
                en: img_en,
                pl: img_pl,
                ru: img_ru
            }
        }
    }
}
</script>

<style>

body {
    background: #020631;
    font: 14px 'Nunito', sans-serif;
    background: url("./assets/mathbg.png") center/cover;
    height: 100vh;
    overflow: hidden;
}

.light_mode_text {
    color: white;
    margin-left: auto;
    margin-right: auto;
    width: 25em;
}

img {
    display: block;
    margin-left: auto;
    margin-right: auto;
    max-width: 50%;
    height: auto;
}
</style>