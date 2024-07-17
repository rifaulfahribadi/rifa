<template>
  <div class="edrea_tm_section" id="blog">
    <div class="section_inner">
      <div class="edrea_tm_news swiper-section">
        <div class="edrea_tm_main_title">
          <h3>Portofolio <span class="coloring">& Article</span></h3>
        </div>
        <div class="news_list">
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
            <swiper-slide class="swiper-slide" v-for="(data, i) in newsData" :key="i">
              <div class="list_inner">
                <div class="image">
                  <img src="img/thumbs/4-3.jpg" alt="" />
                  <div class="main" :data-img-url="data.img"></div>
                  <a class="edrea_tm_full_link news_popup" href="#"></a>
                </div>
                <div class="details">
                  <h3>
                    <a href="#">{{ data.title }}</a>
                  </h3>
                  <span><a href="#">{{ data.tag }}</a></span>
                </div>

                <!-- News Popup Informations -->
                <div class="edrea_tm_hidden_content">
                  <div class="news_popup_details">
                    <div class="top_image">
                      <img src="img/thumbs/4-2.jpg" alt="" />
                      <div class="main" :data-img-url="data.img"></div>
                    </div>
                    <div class="news_main_title">
                      <h3>{{ data.title }}</h3>
                      <span><a href="#">{{ data.tag }}</a></span>
                      <div></div>
                    </div>
                    <div class="text">
                      <p v-for="(text, t) in data.des" :key="t">
                        {{ text }}
                      </p>
                      <br>
                      <div class="edrea_tm_button" id="aboutPopup">
                        <a target="_blank" :href="data.link">More</a>
                      </div> 
                    </div>
                  </div>
                </div>
                <!-- /News Popup Informations -->
              </div>
            </swiper-slide>
            <div class="edrea_tm_swiper_progress fill">
              <div class="my_pagination_in">
                <span class="currentBlogs">0</span>
                <span class="pagination_progress"><span class="all allBlogs"><span></span></span></span>
                <span class="totalBlogs">05</span>
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
import { Navigation, Pagination } from "swiper";
import { Swiper, SwiperSlide } from "swiper/vue";
import { swiperSliderCustomSlider } from "../utilits";

export default {
  name: `BlogComponent`,
  components: {
    Swiper,
    SwiperSlide,
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
          swiperSliderCustomSlider(
            current,
            total,
            "currentBlogs",
            "totalBlogs",
            "allBlogs"
          );
        },
      },
    };
  },
  data() {
    return {
      newsData: [
        {
          title: "Unlocking the Secrets of Exceptional CX",
          img: "img/news/1.jpg",
          tag: "Article",
          link: "https://tender-cadet-d59.notion.site/Unlocking-the-Secrets-of-Exceptional-Customer-Experience-bfe39548dfce48be95c530f0b17f5700?pvs=4",
          des: [
            "Pengalaman pelanggan (CX) adalah faktor kunci dalam menentukan kesuksesan produk. Dengan mengadopsi pendekatan yang berpusat pada pengguna, perusahaan dapat memastikan setiap interaksi memberikan nilai tambah.",
            "Mengidentifikasi dan memahami pelanggan yang tidak puas adalah langkah pertama dalam membangun produk yang lebih baik. Empati dan pemahaman mendalam memungkinkan perusahaan mengubah tantangan menjadi peluang inovasi.",
            "Loyalitas pelanggan di era digital lebih dari sekadar kepuasan; ini tentang membangun koneksi emosional. Personalisasi dan pengalaman yang mulus adalah elemen penting dalam menciptakan loyalitas yang tahan lama.",
            "Customer Identity and Access Management (CIAM) menyediakan pandangan 360 derajat tentang pelanggan, membuka pintu bagi personalisasi dan keamanan yang ditingkatkan.",
            "Insight dari CX Connect Conference menekankan pentingnya tindakan cepat dan efektif dalam menerapkan wawasan yang diperoleh, dari memperkuat peta empati hingga menyempurnakan perjalanan pelanggan.",
          ],
        },
        {
          title: "Product Managers: Beyond Feature Creation",
          img: "img/news/2.jpg",
          tag: "Article",
          link: "https://tender-cadet-d59.notion.site/Product-Managers-Beyond-Feature-Creation-7da11dcce430430983e688dd3e69702a?pvs=4",
          des: [
            "Product Managers tidak hanya bertanggung jawab untuk menciptakan fitur-fitur baru. Tugas utama mereka adalah memahami dan menyelesaikan masalah pengguna.",
            "Fokus utama seorang Product Manager harus pada identifikasi masalah pengguna dan mencari solusi yang efektif. Ini memastikan fitur yang dikembangkan benar-benar bermanfaat.",
            "Pendekatan yang berpusat pada pengguna membantu dalam mengidentifikasi kebutuhan nyata dan menyelaraskan pengembangan produk dengan harapan pengguna.",
            "Kolaborasi dengan tim lintas fungsi adalah kunci dalam menciptakan solusi inovatif yang memenuhi kebutuhan pengguna dan bisnis.",
            "Dengan selalu berfokus pada pemecahan masalah pengguna, Product Managers dapat menciptakan produk yang lebih relevan dan bernilai tinggi bagi pasar.",
          ],
        },
        {
          title: "Ensuring Impactful Prioritization as a PM",
          img: "img/news/3.jpg",
          tag: "Article",
          link: "https://tender-cadet-d59.notion.site/Ensuring-Impactful-Prioritization-as-a-Product-Manager-dd6b9fb213e74f479e2ec92716a2510f?pvs=4",
          des: [
            "Product Managers harus memastikan bahwa prioritas yang ditentukan memberikan dampak signifikan pada produk. Ini melibatkan evaluasi mendalam dan analisis data.",
            "Menggunakan kerangka kerja seperti RICE (Reach, Impact, Confidence, Effort) dapat membantu dalam menentukan prioritas yang tepat.",
            "Kolaborasi dengan tim lintas fungsi dan mendapatkan masukan dari stakeholder kunci sangat penting untuk validasi keputusan prioritas.",
            "Pemantauan dan evaluasi berkelanjutan dari hasil implementasi prioritas memastikan bahwa keputusan yang diambil memberikan hasil yang diharapkan.",
            "Dengan pendekatan yang sistematis dan berbasis data, Product Managers dapat memastikan bahwa prioritas yang ditetapkan benar-benar memberikan nilai tambah bagi produk dan pengguna.",
          ],
        },
        {
          title: "Mastering Agile: Practices and Pitfalls",
          img: "img/news/4.jpg",
          tag: "Article",
          link: "https://tender-cadet-d59.notion.site/Mastering-Agile-Practices-and-Pitfalls-7f74933b4b3d46f88288333cce3207cf?pvs=4",
          des: [
            "Agile methodology adalah pendekatan manajemen proyek yang berfokus pada iterasi cepat dan respons terhadap perubahan.",
            "Kesalahan umum dalam Agile meliputi kurangnya komunikasi, dokumentasi yang tidak memadai, dan kegagalan dalam mengadaptasi perubahan.",
            "Agile yang benar melibatkan kolaborasi tim yang kuat, umpan balik berkelanjutan, dan iterasi yang cepat untuk terus meningkatkan produk.",
            "Menekankan pada nilai-nilai inti Agile seperti kolaborasi tim, tanggapan terhadap perubahan, dan pengiriman perangkat lunak yang berfungsi secara teratur.",
            "Dengan menghindari kesalahan umum dan berfokus pada prinsip-prinsip Agile, tim dapat mencapai efisiensi dan efektivitas yang lebih tinggi dalam pengembangan produk.",
          ],
        },
      ],
    };
  },
};
</script>
