<template>
  <div>
    <div id="top">
      <swiper class="swiper" :slides-per-view="1" :space-between="50" @swiper="onSwiper" @slideChange="onSlideChange">
        <swiper-slide style="background-image:url(/top1.jpg)" class="slide">
          <swiper-slide style="background-image:url(/top2.jpg)" class="slide">
            <swiper-slide style="background-image:url(/top3.jpg)" class="slide"></swiper-slide>
          </swiper-slide>
          <div class="header"> 명지전문대 정보통신공학과 엄정식
          </div>
        </swiper-slide>


        <swiper-slide class="slide">Slide 2</swiper-slide>
        <swiper-slide style="background-image:url(/top2.jpg)" class="slide">
          <div class="header"> 명지전문대 정보통신공학과 엄정식
          </div>
        </swiper-slide>

        <swiper-slide class="slide">Slide 3</swiper-slide>
        <swiper-slide style="background-image:url(/top3.jpg)" class="slide">
          <div class="header"> 명지전문대 정보통신공학과 엄정식
          </div>
        </swiper-slide>
      </swiper>

    </div>

    <div id="portfolio">
      <div class="header"> 포토폴리오</div>

      <div class="list">
        <div class="item" @click="movePage('/portfolio1')" data-aos="zoom-out-right"
          style="background-image:ur1(/top2.jpg)"></div>
        <div class="item" data-aos="zoom-in-left" style="background-image:ur1(/top2.jpg)"></div>
        <div class="item" data-aos="fade-up" data-aos-duration="3000" style="background-image:ur1(/top2.jpg)"></div>
        <div class="item" data-aos="fade-right" data-aos-offset="3000" style="background-image:ur1(/top2.jpg)"></div>
        <div class="item" style="background-image:ur1(/top2.jpg)"></div>


      </div>

    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue';

// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';

// Import Swiper styles
import 'swiper/css';

import aos from "aos";

export default defineComponent({
  name: 'HomeView',


  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const onSwiper = (swiper) => {
      console.log(swiper);
    };
    const onSlideChange = () => {
      console.log('slide change');
    };
    return {
      onSwiper,
      onSlideChange,
    };
  },
  mounted() {
    aos.init();
  },
  methods: {
    modvePage(path) {
      this.$router.push(path)
    }
  },
  name: 'HomeVeiw',
});
</script>

<style lang="less">
#top {
  height: 100vh;

  .swiper {
    height: 100vh;

    .slide {
      background-position: center center;
      background-size: cover;
      text-align: center;
      vertical-align: middle;

      //헤더 가운데 정렬
      .header {
        font-size: 20px;
        font-weight: 900;
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
      }
    }
  }
}

#protfolio {
  .header {
    text-align: center;
    font-size: 60px;
  }

  .list {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 10px;

    .item {
      width: 100%;
      background-position: center center;
      background-size: cover;
      aspect-ratio: 1 / 1;
      border-radius: 10px;
    }

  }
}
</style>