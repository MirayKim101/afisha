<template>
  <header class="header">
    <div class="header__wrapper container">
      <a href="/" class="header__logo">
        <img src="/images/header_logo.svg" alt="">
      </a>

      <nav aria-label="Главное меню в шапке сайта" class="header__navigation">
        <ul class="header__navigation-list">

          <li class="header__navigation-list-item"
              v-for="link in links">
            <NuxtLink
                class="header__navigation-list-item-link"
                :to="link.link">
              {{ link.title }}
            </NuxtLink>
          </li>
          <button @click="isVisibleModal = true" style="color: #fff;">Регистрация</button>
          <button @click="showModal = true" style="color: #fff;">Вход</button>
        </ul>
      </nav>

      <div class="header__panel">
        <div class="header__panel-search">
          <svg xmlns="http://www.w3.org/2000/svg" width="34" height="34" viewBox="0 0 34 34" fill="none">
            <path fill-rule="evenodd" clip-rule="evenodd"
                  d="M7.1498 22.4916C2.91328 18.255 2.91328 11.3863 7.1498 7.1498C11.3863 2.91328 18.255 2.91328 22.4916 7.1498C26.7281 11.3863 26.7281 18.255 22.4916 22.4916C18.255 26.7281 11.3863 26.7281 7.1498 22.4916ZM5.75509 5.75509C0.748303 10.7619 0.748303 18.8795 5.75509 23.8863C10.4842 28.6153 17.9885 28.8776 23.0255 24.6732L30.3523 32L31.747 30.6053L24.4394 23.2977C28.8857 18.2623 28.7013 10.5701 23.8863 5.75509C18.8795 0.748303 10.7619 0.748304 5.75509 5.75509Z"
                  fill="white"/>
          </svg>
        </div>

        <button class="header__panel-account">
          <svg xmlns="http://www.w3.org/2000/svg" width="30" height="32" viewBox="0 0 30 32" fill="none">
            <path fill-rule="evenodd" clip-rule="evenodd"
                  d="M7.5625 9.61114C7.5625 5.38832 10.9115 2 15 2C19.0885 2 22.4375 5.38832 22.4375 9.61114C22.4375 13.8223 19.1069 17.2036 15.0338 17.2222C15.0225 17.2222 15.0113 17.2222 15 17.2222C14.9887 17.2222 14.9775 17.2222 14.9662 17.2222C10.8931 17.2036 7.5625 13.8223 7.5625 9.61114ZM10.3722 17.9902C7.49627 16.3389 5.5625 13.1972 5.5625 9.61114C5.5625 4.32236 9.76871 0 15 0C20.2313 0 24.4375 4.32236 24.4375 9.61114C24.4375 13.1972 22.5037 16.3389 19.6278 17.9902C25.3753 19.9607 29.5 25.5003 29.5 32H27.5C27.5 24.9358 21.9037 19.2417 15.0354 19.2222C15.0236 19.2223 15.0118 19.2223 15 19.2223C14.9882 19.2223 14.9764 19.2223 14.9646 19.2222C8.0963 19.2417 2.5 24.9358 2.5 32H0.5C0.5 25.5003 4.62468 19.9607 10.3722 17.9902Z"
                  fill="white"/>
          </svg>
        </button>
      </div>
    </div>
  </header>

  <AuthModal :show="showModal" @close="showModal = false">
    <template #heading>
      <h2> Вход в личный кабинет</h2>
      <button @click="showModal = false">
        <svg xmlns="http://www.w3.org/2000/svg" width="53" height="53" viewBox="0 0 53 53" fill="none">
          <rect x="12.374" y="13.7891" width="2" height="37" transform="rotate(-45 12.374 13.7891)" fill="black"/>
          <rect x="13.7886" y="39.9517" width="2" height="37" transform="rotate(-135 13.7886 39.9517)" fill="black"/>
        </svg>
      </button>

    </template>
  </AuthModal>

  <RegistrationModal :isVisibleModal="isVisibleModal" @close="isVisibleModal = false">
    <template #heading>
      <h2> Регистрация</h2>
      <button @click="isVisibleModal = false">
        <svg xmlns="http://www.w3.org/2000/svg" width="53" height="53" viewBox="0 0 53 53" fill="none">
          <rect x="12.374" y="13.7891" width="2" height="37" transform="rotate(-45 12.374 13.7891)" fill="black"/>
          <rect x="13.7886" y="39.9517" width="2" height="37" transform="rotate(-135 13.7886 39.9517)" fill="black"/>
        </svg>
      </button>

    </template>
  </RegistrationModal>
</template>

<script setup>

import AuthModal from "~/components/modals/AuthModal.vue";
import RegistrationModal from "~/components/modals/RegistrationModal.vue";

const showModal = ref(false)
const isVisibleModal = ref(false)


const links = ref([
  {title: 'Главная', link: '/'},
  {title: 'Заведения', link: '/asdwd'},
  {title: 'События', link: '/asdwd'},
  {title: 'Фотоотчеты', link: '/adwsd'},
  {title: 'Заказать фотосъемку', link: '/ww'},
  {title: 'Личный кабинет', link: '/account'},

])
</script>

