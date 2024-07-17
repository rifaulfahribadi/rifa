<template>
  <div class="edrea_tm_section" id="awards">
    <div class="section_inner">
      <div class="edrea_tm_portfolio swiper-section">
        <div class="edrea_tm_main_title">
          <h3>Latest <span class="coloring">Achievements</span></h3>
        </div>
        <div class="portfolio_list gallery_zoom">
          <swiper :loop="false" :slidesPerView="1" :spaceBetween="0" :loopAdditionalSlides="1" :autoplay="{
            delay: 6000,
          }" :navigation="{
            nextEl: '.my_next',
            prevEl: '.my_prev',
          }" :pagination="pagination" :breakpoints="{
            700: {
              slidesPerView: 2,
              spaceBetween: 20,
            },
            1200: {
              slidesPerView: 3,
              spaceBetween: 30,
            },
          }" @slideChange="onSlideChange" :modules="modules" class="swiper-container">
            <swiper-slide v-for="(item, index) in projects" :key="index" class="swiper-slide">
              <div class="list_inner">
                <div class="image">
                  <img :src="item.image" alt="" />
                  <div class="main" :data-img-url="item.image"></div>
                </div>
                <div class="details">
                  <h3>{{ item.title }}</h3>
                  <span>{{ item.description }}</span>
                </div>
                <!-- <a class="edrea_tm_full_link popup-vimeo" target="_blank" :href="item.link"></a> -->
                <a class="edrea_tm_full_link" target="_blank" :href="item.link"></a>
              </div>
            </swiper-slide>
            <div class="edrea_tm_swiper_progress fill">
              <div class="my_pagination_in">
                <span class="current">0</span>
                <span class="pagination_progress"><span class="all"><span style="
                        transform: translate3d(0px, 0px, 0px) scaleX(0.75)
                          scaleY(1);
                      "></span></span></span>
                <span class="total">04</span>
              </div>
              <div class="my_navigation">
                <ul>
                  <li>
                    <a class="my_prev" href="#"><i class="icon-left-open-1"></i></a>
                  </li>
                  <li>
                    <a class="my_next" href="#"><i class="icon-right-open-1"></i></a>
                  </li>
                </ul>
              </div>
            </div>
          </swiper>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import Swiper core and required modules

// Import Swiper Vue.js components
import { Navigation, Pagination } from "swiper";
import { Swiper, SwiperSlide } from "swiper/vue";
import { swiperSliderCustomSlider } from "../utilits";

export default {
  name: `AwardsComponent`,
  components: {
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      projects: [
        {
          title: 'Abc',
          description: 'xxxx',
          image: 'img/portfolio/7.jpg',
          link: 'https://rifaulfahribadi.github.io'
        },
        {
          title: 'BCD',
          description: 'yyyy',
          image: 'img/portfolio/7.jpg',
          link: 'link'
        }
      ],
    };
  },
  methods: {
    onSlideChange(swiper) {
      this.activeSlider = swiper.activeIndex + 1;
    },
  },
  setup() {
    return {
      modules: [Navigation, Pagination],
      pagination: {
        el: ".edrea_tm_swiper_progress",
        type: "custom", // progressbar
        renderCustom: function (swiper, current, total) {
          swiperSliderCustomSlider(current, total);
        },
      },
    };
  },
};
</script>
