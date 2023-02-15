<template>
  <div class="contact">
    <h1>Contact Us</h1>
    <TransitionGroup appear tag="ul" name="contactUl" @before-enter="beforeEnter" @enter="Enter">
      <li v-for="(icon, index ) in icons" :key="icon.name" :data-index="index">
        <span class="material-icons">{{ icon.name }}</span>
        <div>{{ icon.text }}</div>
      </li>
    </TransitionGroup>
  </div>
</template>

<script>
import { ref } from 'vue';
import gsap from 'gsap';

export default {
  setup() {
    const icons = ref([
      { name: 'alternate_email', text: 'by email' },
      { name: 'local_phone', text: 'by phone' },
      { name: 'local_post_office', text: 'by post' },
      { name: 'local_fire_department', text: 'by smoke signal' },
    ]);

    const beforeEnter = (el) => {
      console.log("before enter");
      el.style.opacity = "0";
      el.style.transform = "translateY(100px)"
    }
    const Enter = (el, done) => {
      console.log("enter");
      gsap.to(el, {
        y: 0,
        opacity: 1,
        duration: 0.8,
        delay: el.dataset.index * 0.4,
        onComplete: done
      })
    }
    return { icons, beforeEnter, Enter }
  }
}
</script>

<style>
body {
  background-color: #F6E7D8;
}
.contact h1 {
  color: #C65D7B;
}

.contact ul {
  font-weight: 500;
  font-family: 'Roboto Condensed', sans-serif;
  text-transform: uppercase;
  display: grid;
  padding: 0;
  grid-template-columns: 1fr 1fr;
  grid-gap: 20px;
  max-width: 400px;
  margin: 60px auto;
}

.contact li {
  list-style-type: none;
  background: white;
  padding: 30px;
  border-radius: 10px;
  box-shadow: 1px 3px 5px rgba(0, 0, 0, 0.1);
  cursor: pointer;
  line-height: 1.5em;
  color: #8D8DAA;
}

.contact .material-icons {
  color: #F68989;
  font-size: 2rem;
}
</style>