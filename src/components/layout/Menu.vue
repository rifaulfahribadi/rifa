<template>
  <ul class="transition_link">
    <li :class="navFuntions.activeNavCls('home')">
      <a href="#home" @click="navFuntions.activeSection('home')">Home</a>
    </li>
    <li :class="navFuntions.activeNavCls('about')">
      <a href="#about" @click="navFuntions.activeSection('about')">About</a>
    </li>
    <li :class="navFuntions.activeNavCls('awards')">
      <a href="#awards" @click="navFuntions.activeSection('awards')"
        >Awards</a
      >
    </li>
    <li :class="navFuntions.activeNavCls('portofolio')">
      <a href="#portofolio" @click="navFuntions.activeSection('portofolio')">Portofolio</a>
    </li>
    <li :class="navFuntions.activeNavCls('blog')">
      <a href="#blog" @click="navFuntions.activeSection('blog')"
        >Blog</a
      >
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
