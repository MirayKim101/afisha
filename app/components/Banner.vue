<template>
  <section class="banner">
    <div class="banner__wrapper container">
      <div class="banner__content">

        <div class="banner__content-info">
          <p class="banner__content-info-subtitle">
            АРТ ПРОСТРАНСТВО KLUMBA SPACE
          </p>
          <h1 class="banner__content-info-title">
            Кавер-бэнд
            «В Главных ролях »
          </h1>
        </div>

        <NuxtLink class="banner__content-link" to="/">
          Посмотреть
          <svg xmlns="http://www.w3.org/2000/svg" width="47" height="14" viewBox="0 0 47 14" fill="none">
            <path d="M1 7L45.5005 7M45.5005 7L39.4856 13M45.5005 7L39.4856 1" stroke="#FCF8EB" stroke-width="1.5"
                  stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </NuxtLink>
      </div>
    </div>
    <div class="banner__overlay">
      <NuxtImg
          class="banner__overlay-img"
          src="/images/banner_img.jpg"
          alt="Картинка мероприятия на главном экране"
      />
    </div>

  </section>
</template>

<script setup>

</script>

<style lang="scss" scoped>

</style>