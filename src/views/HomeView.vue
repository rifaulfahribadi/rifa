<template>
  <MfpPopup />
  <EdreaPopup />
  <AboutPopup />
  <PreloaderComponent />
  <div
    class="edrea_tm_all_wrap"
    data-magic-cursor="show"
    data-enter="fadeInUp"
    data-exit=""
  >
    <!-- WAVE DOTS -->
    <div class="waves"></div>
    <!-- WAVE DOTS -->

    <!-- SETTINGS -->
    <SettingsComponent />
    <!-- HEADER -->
    <HeaderComponent />
    <!-- /HEADER -->

    <!-- CONTENT -->
    <div class="edrea_tm_content">
      <!-- HOME -->
      <HomeComponent />
      <!-- /HOME -->

      <!-- ABOUT -->
      <AboutComponent />
      <!-- /ABOUT -->

      <!-- PORTFOLIO -->
      <AwardsComponent />
      <!-- /PORTFOLIO -->

      <!-- PORTFOLIO -->
      <BlogComponent />
      <!-- /PORTFOLIO -->

      <!-- NEWS -->
      <PortofolioComponent />
      <!-- /NEWS -->

      <!-- CONTACT -->
      <ContactComponent />
      <!-- /CONTACT -->
    </div>
    <!-- /CONTENT -->

    <!-- MAGIC CURSOR -->
    <CursorComponent />
    <!-- /MAGIC CURSOR -->
  </div>
</template>

<script>
import PreloaderComponent from "@/components/layout/PreloaderComponent.vue";

import AboutPopup from "@/components/popup/AboutPopup.vue";
import EdreaPopup from "@/components/popup/EdreaPopup.vue";
import MfpPopup from "@/components/popup/MfpPopup.vue";
import AboutComponent from "../components/AboutComponent.vue";
import ContactComponent from "../components/ContactComponent.vue";
import HomeComponent from "../components/HomeComponent.vue";
import CursorComponent from "../components/layout/CursorComponent.vue";
import HeaderComponent from "../components/layout/HeaderComponent.vue";
import SettingsComponent from "../components/layout/SettingsComponent.vue";
import PortofolioComponent from "../components/PortofolioComponent.vue";
import AwardsComponent from "../components/AwardsComponent.vue";
import BlogComponent from "../components/BlogComponent.vue";
import { dataImage, imgToSVG } from "../utilits";
import { waves } from "../waves";

export default {
  name: `HomeView`,
  mounted() {
    waves();
    imgToSVG();
    dataImage();
  },
  components: {
    HomeComponent,
    HomeComponent,
    AboutComponent,
    PortofolioComponent,
    ContactComponent,
    HeaderComponent,
    SettingsComponent,
    CursorComponent,
    AwardsComponent,
    BlogComponent,
    PreloaderComponent,
    MfpPopup,
    EdreaPopup,
    AboutPopup,
  },
};
</script>

<!-- about chart -->
