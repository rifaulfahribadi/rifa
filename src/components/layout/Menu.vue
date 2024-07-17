<template>
  <ul class="transition_link">
    <li :class="navFuntions.activeNavCls('home')">
      <a href="#home" @click="navFuntions.activeSection('home')">Home</a>
    </li>
    <li :class="navFuntions.activeNavCls('about')">
      <a href="#about" @click="navFuntions.activeSection('about')">About</a>
    </li>
    <li :class="navFuntions.activeNavCls('portfolio')">
      <a href="#awards" @click="navFuntions.activeSection('portfolio')"
        >Awards</a
      >
    </li>
    <li :class="navFuntions.activeNavCls('news')">
      <a href="#portofolio" @click="navFuntions.activeSection('news')">Portofolio</a>
    </li>
    <li :class="navFuntions.activeNavCls('contact')">
      <a href="#contact" @click="navFuntions.activeSection('contact')"
        >Contact</a
      >
    </li>
  </ul>
</template>

<script>
import { navFuntions } from "@/navFuntions";
export default {
  name: `Menu`,
  data() {
    return {
      navFuntions,
    };
  },
};
</script>
