<template>
  <div class="edrea_tm_modalbox" :class="open ? 'opened' : ''">
    <div class="box_inner">
      <div class="close">
        <a href="#" @click="close"><i class="icon-cancel"></i></a>
      </div>
      <div class="description_wrap">
        <div class="about_popup_details">
          <div class="left">
            <div class="left_inner">
              <div class="author">
                <div class="avatar_image">
                  <img src="img/thumbs/1-1.jpg" alt="" />
                  <div class="main" data-img-url="img/about/2.jpg"></div>
                </div>
                <div class="short">
                  <h3 class="name">
                    {{ aboutData.firstName }}
                    <span class="coloring">{{ aboutData.lastName }}</span>
                  </h3>
                  <h3 class="job">
                    <AnimationText />
                  </h3>
                </div>
              </div>
              <div class="list">
                <ul>
                  <li>
                    <div class="list_inner">
                      <i class="icon-user"></i>
                      <span
                        >{{ aboutData.firstName }}
                        {{ aboutData.lastName }}</span
                      >
                    </div>
                  </li>
                  <li>
                    <div class="list_inner">
                      <i class="icon-location"></i>
                      <span
                        ><a href="#" class="href_location">{{
                          aboutData.address
                        }}</a></span
                      >
                    </div>
                  </li>
                  <li>
                    <div class="list_inner">
                      <i class="icon-phone"></i>
                      <span
                        ><a :href="`https://wa.me/683839075330`" target="_blank">{{ 
                        aboutData.phn 
                        }}</a></span
                      >
                    </div>
                  </li>
                  <li>
                    <div class="list_inner">
                      <i class="icon-mail-1"></i>
                      <span
                        ><a :href="`mailto:${aboutData.email}`" target="_blank">{{
                          aboutData.email
                        }}</a></span
                      >
                    </div>
                  </li>
                </ul>
              </div>
              <div class="edrea_tm_button full">
                <a href="https://drive.google.com/drive/folders/1CDI3TuRIMbpV0otxO2QqAIKvj3VjWxMc?usp=sharing" target="_blank" download>Download CV</a>
              </div>
            </div>
          </div>
          <div class="right">
            <div class="right_inner">
              <div class="biography">
                <div class="about_title">
                  <h3>
                    <span>About <span class="coloring">Me</span></span>
                  </h3>
                </div>
                <div class="text">
                  <p>
                    Hello everybody! My name is
                    <span>Rifa Ulfah Ribadi.</span> I am a Associate Product Manager in an e-commerce enabler startup.
                    Led the integration of an AI product for automatic landing page creation, achieving significant efficiency improvements within 2 months.
                    Focused on data-driven problem solving and strong team leadership, aspiring to advance product innovation in technology industries with a solid business foundation.
                  </p>
                </div>
              </div>
              <div class="service">
                <div class="about_title">
                  <h3>
                    <span>Profesional <span class="coloring"> Skills</span></span>
                  </h3>
                </div>
                <div class="list">
                  <ul>
                    <li v-for="(service, i) in aboutData.serviceLists" :key="i">
                      <i class="icon-right-dir"></i>{{ service }}
                    </li>
                  </ul>
                </div>
              </div>
              <div class="timeline">
                <div class="about_title">
                  <h3>
                    <span>Professional <span class="coloring"> Experiences</span></span>
                  </h3>
                </div>
                <div class="list">
                  <ul>
                    <li v-for="(work, i) in aboutData.working" :key="i">
                      <div class="list_inner">
                        <div class="time">
                          <span>{{ work.year }}</span>
                        </div>
                        <div class="place">
                          <h3>{{ work.company }}</h3>
                          <span>{{ work.deg }}</span>
                        </div>
                      </div>
                    </li>
                  </ul>
                </div>
              </div>
              <div class="partners">
                <div class="about_title">
                  <h3>
                    <span>Product <span class="coloring">Handled</span></span>
                  </h3>
                </div>
                <div class="list">
                  <ul>
                    <li v-for="(partner, i) in aboutData.partnersLogos" :key="i">
                      <div class="list_inner">
                        <a :href="partner.url" target="_blank">
                          <img :src="partner.img" alt="" />
                        </a>
                      </div>
                    </li>
                  </ul>
                </div>
              </div>
              <div class="timeline">
                <div class="about_title">
                  <h3>
                    <span
                      >Education <span class="coloring">Background</span></span
                    >
                  </h3>
                </div>
                <div class="list">
                  <ul>
                    <li v-for="(edu, i) in aboutData.education" :key="i">
                      <div class="list_inner">
                        <div class="time">
                          <span>{{ edu.year }}</span>
                        </div>
                        <div class="place">
                          <h3>{{ edu.unv }}</h3>
                          <span>{{ edu.degree }}</span>
                        </div>
                      </div>
                    </li>
                  </ul>
                </div>
              </div>
              <div class="prog_skill">
                <div class="about_title">
                  <h3>
                    <span>Language <span class="coloring">Skills</span></span>
                  </h3>
                </div>
                <div class="circular_progress_bar">
                  <ul>
                    <li>
                      <div class="list_inner">
                        <div class="myCircle" data-value="0.80"></div>

                        <div class="title"><span>English</span></div>
                      </div>
                    </li>
                    <li>
                      <div class="list_inner">
                        <div class="myCircle" data-value="1.0"></div>

                        <div class="title"><span>Indonesia</span></div>
                      </div>
                    </li>
                    <li>
                      <div class="list_inner">
                        <div class="myCircle" data-value="-1.0"></div>

                        <div class="title"><span>Woman</span></div>
                      </div>
                    </li>
                  </ul>
                </div>
              </div>
              <div class="testimonial">
                <div class="about_title">
                  <h3>
                    <span>Career <span class="coloring">Motto </span></span>
                  </h3>
                </div>
                <div class="list">
                  <swiper
                    :loop="true"
                    :slidesPerView="1"
                    :spaceBetween="10"
                    :loopAdditionalSlides="1"
                    :autoplay="{
                      delay: 6000,
                    }"
                    :modules="modules"
                    class="owl-carousel"
                  >
                    <swiper-slide>
                      <div class="list_inner">
                        <div class="text">
                          <i class="icon-quote-left"></i>
                          <p>
                            Don't be a feature creation machine, be a stand out problem solver.
                          </p>
                        </div>
                        <div class="details">
                          <div class="image">
                            <div
                              class="main"
                              data-img-url="img/testimonials/rifa.jpg"
                            ></div>
                          </div>
                          <div class="info">
                            <h3>Rifa Ulfah Ribadi</h3>
                            <span>Product Manager</span>
                          </div>
                        </div>
                      </div>
                    </swiper-slide>
                    <swiper-slide>
                      <div class="list_inner">
                        <div class="text">
                          <i class="icon-quote-left"></i>
                          <p>
                            A little different is much better than a little better.
                          </p>
                        </div>
                        <div class="details">
                          <div class="image">
                            <div
                              class="main"
                              data-img-url="img/testimonials/panji.jpg"
                            ></div>
                          </div>
                          <div class="info">
                            <h3>Panji Pragiwaksono</h3>
                            <span>Stand-up Comedian</span>
                          </div>
                        </div>
                      </div>
                    </swiper-slide>
                    <swiper-slide>
                      <div class="list_inner">
                        <div class="text">
                          <i class="icon-quote-left"></i>
                          <p>
                            Aligning product vision with user needs, 
                            while encouraging innovation and collaboration 
                            within teams to create solutions with real impact.
                          </p>
                        </div>
                        <div class="details">
                          <div class="image">
                            <div
                              class="main"
                              data-img-url="img/testimonials/ken.jpg"
                            ></div>
                          </div>
                          <div class="info">
                            <h3>Ken Norton</h3>
                            <span>Program Manager</span>
                          </div>
                        </div>
                      </div>
                    </swiper-slide>
                  </swiper>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { Navigation, Pagination } from "swiper";
import { Swiper, SwiperSlide } from "swiper/vue";
import AnimationText from "../AnimationText.vue";
export default {
  name: `AboutPopup`,
  components: {
    Swiper,
    SwiperSlide,
    AnimationText,
  },
  data() {
    return {
      open: false,
      // data
      aboutData: {
        firstName: "Rifa Ulfah",
        lastName: "Ribadi",
        address: "Jakarta, Indonesia",
        phn: "+62 838 8907 5330",
        email: "rifaulfahribadi@gmail.com",
        serviceLists: [
          "Product Management",
          "Project Management",
          "UI UX Design",
          "Product Research",
          "Business Consultant",
        ],
        skills: {
          programming: [
            { name: "WordPress", value: "95" },
            { name: "JavaScript", value: "80" },
            { name: "Angular", value: "90" },
          ],
          language: [
            { name: "English", value: "95" },
            { name: "Russian", value: "80" },
            { name: "Arabic", value: "90" },
          ],
        },
        education: [
          {
            year: "2019 - 2023",
            unv: "State Polytechnic of Jember",
            degree: "D4 - Agroindustry Management",
          },
          {
            year: "2022 - 2022",
            unv: "Binar Academy",
            degree: "Bootcamp - Product Management",
          },
          {
            year: "2023 - 2023",
            unv: "Rakamin Academy",
            degree: "Bootcamp - Product Management",
          },
        ],
        working: [
          {
            year: "Feb 24 - now",
            company: "Holic Technology Indonesia",
            deg: "Product Operation",
          },
          {
            year: "Aug 23 - now",
            company: "PT. Kampung Marketerindo Berdaya (Komerce)",
            deg: "Product Manager",
          },
          {
            year: "Mar 24 - Jul 24",
            company: "InTernak",
            deg: "Project Manager",
          },
          {
            year: "Dec 23 - May 24",
            company: "Wiz Technology",
            deg: "Project Manager",
          },
          {
            year: "May 23 - Dec 23",
            company: "Rakamin Academy",
            deg: "CC Product Management Bootcamp",
          },
          {
            year: "Apr 23 - Jul 23",
            company: "Bumi Scholar",
            deg: "Project Manager",
          },
        ],
        partnersLogos: [
          { img: "img/partners/6.png", url: "https://focustic.id" },
          { img: "img/partners/7.png", url: "https://internak.id" },
          { img: "img/partners/8.png", url: "https://komads.id/whatsapp" },
          { img: "img/partners/9.png", url: "komform.id" },
          { img: "img/partners/10.png", url: "kompage.id" },
          { img: "img/partners/6.png", url: "https://rifaulfahribadi.github.io" },
        ],
      },
    };
  },
  methods: {
    close() {
      this.open = false;
    },
  },
  mounted() {
    const aboutPopup = document.getElementById("aboutPopup");
    aboutPopup.addEventListener("click", () => {
      this.open = true;
    });

    const myCircle = document.querySelectorAll(".myCircle");
    myCircle.forEach((circle) => {
      let progress = circle.getAttribute("data-value");
      let span = document.createElement("span");
      span.className = "number";
      const value = `${progress * 100}%`;
      span.innerHTML = value;
      circle.appendChild(span);
      circle.style.setProperty("--progress", value);
      circle.setAttribute("aria-valuenow", value);
    });
  },
  setup() {
    return {
      modules: [Navigation, Pagination],
    };
  },
};
</script>

<style scoped>
.testimonial {
  overflow: hidden;
}
.owl-carousel.swiper {
  overflow: unset;
}

.myCircle {
  --hue: 220;
  --holesize: 67%;
  --track-bg: hsl(233, 34%, 92%);

  min-width: 110px;
  min-height: 110px;
  display: grid;
  align-items: center;
  justify-items: center;
  place-items: center;
  position: relative;
  margin-bottom: 5px;
}
.myCircle::before {
  content: "";
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  border-radius: 50%;
  z-index: -1;
  background: conic-gradient(
    var(--main-color) var(--progress, 0%),
    rgba(255, 255, 255, 0.15) var(--progress, 0%) 100%
  );

  mask-image: radial-gradient(
    transparent var(--holesize),
    black calc(var(--holesize) + 1px)
  );
}
</style>
