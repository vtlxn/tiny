<template>
  <main class="main">
    <div class="container">
      <swiper :options="swiperOption" ref="mySwiper">
        <swiper-slide 
          class="main-content"
              v-for="slideItem of slideItems"
              :key="slideItem.id"
        >
          <div class="info">
            <h1 class="info__primary">{{slideItem.titleFirst}}</h1>
            <h2 class="info__secondary">{{slideItem.titleSecond}}</h2>
            <div class="info__decription">{{slideItem.description}}</div>
            <div class="info__icons d-flex">
              <img :src="item" alt="platform"
                v-for="(item, index) in slideItem.icons"
                :key="index"
              >
            </div>
          </div>
          <div class="ipad-img">
            <img 
              class="img-item" 
              :src="slideItem.imgBig" 
              alt="ipad"
            >
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
            clickable: true,
          }
        },
        slideItems: [],
        resource: null

      }
    },
    components: {
      swiper,
      swiperSlide
    },
      created() {
        this.resource = this.$resource('slideinfo')
      },
      mounted() {
        this.loadSlideItems()
      },
      methods: {
        loadSlideItems() {
          this.resource.get().then(response => response.json())
            .then(slideinfo => this.slideItems = slideinfo)
        }
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
