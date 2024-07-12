<template>
  <div class="edrea_tm_section" id="about">
    <div class="section_inner">
      <div class="edrea_tm_about">
        <div class="left">
          <div class="image">
            <img src="img/thumbs/1-1.jpg" alt="" />
            <div class="main" data-img-url="img/about/1.jpg"></div>
          </div>
        </div>
        <div class="right">
          <div class="short">
            <h3 class="name">Rifa <span class="coloring">Ulfah Ribadi</span></h3>
            <h3 class="job">
              <AnimationText />
            </h3>
          </div>
          <div class="text">
            <p>
              My name is <span>Rifa Ulfah Ribadi</span> As an Associate Product Manager in an e-commerce startup,
              led the integration of an AI product for automatic landing page creation, achieving significant efficiency improvements within 2 months
              Focused on data-driven problem solving and strong team leadership, 
              aspiring to advance product innovation in technology industries with a solid business foundation.
            </p>
          </div>
          <div class="edrea_tm_button" id="aboutPopup">
            <a href="#">Don't Click !!</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import AnimationText from "./AnimationText.vue";
export default {
  name: `AboutComponent`,
  data() {
    return {
      open: false,
    };
  },
  components: {
    AnimationText,
  },
};
</script>

<style scoped>
.edrea_tm_modalbox {
  top: -90px;
}
</style>
