<template>
  <main class="main">
    <div class="container">
      <swiper :options="swiperOption" ref="mySwiper" @someSwiperEvent="callback">
        <swiper-slide class="main-content">
          <div class="info">
            <h1 class="info__primary">
              Inspire your inspiration
            </h1>
            <h2 class="info__secondary">
              Simple to use for your app, products showcase and your inspiration
            </h2>
            <div class="info__decription">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent vitae eros eget tellus
              tristique bibendum. Donec rutrum sed sem quis venenatis. Proin viverra risus a eros
              volutpat
              tempor. In quis arcu et eros porta lobortis sit
            </div>
            <div class="info__icons d-flex">
              <img src="../assets/icon-fa-apple.png" alt="apple">
              <img src="../assets/icon-fa-android.png" alt="android">
              <img src="../assets/icon-fa-windows.png" alt="windows">
            </div>
          </div>
          <div class="ipad-img">
            <img class="img-item" src="../assets/ipad-white.png" alt="ipad">
          </div>
        </swiper-slide>
        <swiper-slide class="main-content">
          <div class="info">
            <h1 class="info__primary">
              Inspire your inspiration
            </h1>
            <h2 class="info__secondary">
              Simple to use for your app, products showcase and your inspiration
            </h2>
            <div class="info__decription">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent vitae eros eget tellus
              tristique bibendum. Donec rutrum sed sem quis venenatis. Proin viverra risus a eros
              volutpat
              tempor. In quis arcu et eros porta lobortis sit
            </div>
            <div class="info__icons d-flex">
              <img src="../assets/icon-fa-apple.png" alt="apple">
              <img src="../assets/icon-fa-android.png" alt="android">
              <img src="../assets/icon-fa-windows.png" alt="windows">
            </div>
          </div>
          <div class="ipad-img">
            <img class="img-item" src="../assets/ipad-white.png" alt="ipad">
          </div>
        </swiper-slide>
        <swiper-slide class="main-content">
          <div class="info">
            <h1 class="info__primary">
              Inspire your inspiration
            </h1>
            <h2 class="info__secondary">
              Simple to use for your app, products showcase and your inspiration
            </h2>
            <div class="info__decription">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent vitae eros eget tellus
              tristique bibendum. Donec rutrum sed sem quis venenatis. Proin viverra risus a eros
              volutpat
              tempor. In quis arcu et eros porta lobortis sit
            </div>
            <div class="info__icons d-flex">
              <img src="../assets/icon-fa-apple.png" alt="apple">
              <img src="../assets/icon-fa-android.png" alt="android">
              <img src="../assets/icon-fa-windows.png" alt="windows">
            </div>
          </div>
          <div class="ipad-img">
            <img class="img-item" src="../assets/ipad-white.png" alt="ipad">
          </div>
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
    </div>
    <div class="container">
      <div class="row">
      </div>
    </div>
  </main>
</template>

<script>
  import 'swiper/dist/css/swiper.css'
  import {swiper, swiperSlide} from 'vue-awesome-swiper'

  export default {
    data() {
      return {
        swiperOption: {
          pagination: {
            el: '.swiper-pagination',
            clickable: true
          }
        }
      }
    },
    components: {
      swiper,
      swiperSlide
    }
  }
</script>

<style lang="scss">
  .main {
    background-color: #fcdb00;
    padding-bottom: 60px;

    .main-content {
      display: flex;
      flex-direction: row;
      align-items: center;
      justify-content: space-between;
    }

    .info {
      max-width: 395px;
      padding-bottom: 60px;

      &__primary {
        font-size: 32px;
        font-weight: bold;
        padding-bottom: 10px;
      }

      &__secondary {
        font-size: 20px;
        padding-bottom: 8px;
      }

      &__decription {
        font-size: 16px;
        line-height: 1.3;
        padding-bottom: 40px;
      }

      &__icons {
        justify-content: space-between;
        max-width: 180px;
      }
    }

    .ipad-img {
      display: flex;

      .img-item {
        padding-right: 40px;
      }
    }
  }

  @media (max-width: 992px) {
    .main {
      padding-top: 130px;

      .ipad-img {
        display: none;

        .img-item {
          padding-right: 0;
        }
      }
    }
  }
</style>
