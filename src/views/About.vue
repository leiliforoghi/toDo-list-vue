<template>
  <div class="about">
    <Transition appear @before-enter="beforeEnter" @after-enter="afterEnter" @enter="Enter">
      <h1 v-if="showTitle">About</h1>
    </Transition>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam officia possimus delectus inventore quod
      quisquam culpa voluptas iusto, quae maiores quo dolorum, corporis laboriosam a dolore consequatur assumenda nam!
    </p>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam officia possimus delectus inventore quod
      quisquam culpa voluptas iusto, quae maiores quo dolorum, corporis laboriosam a dolore consequatur assumenda nam!
    </p>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam officia possimus delectus inventore quod
      quisquam culpa voluptas iusto, quae maiores quo dolorum, corporis laboriosam a dolore consequatur assumenda nam!
    </p>
  </div>
</template>

<script>
import { ref } from 'vue';
import gsap from 'gsap';

export default {
  setup() {
    const showTitle = ref(true);

    const beforeEnter = (el) => {
      console.log('before', el);
      el.style.transform = "translateY(-60px)";
      el.style.opacity = "0";
    }
    const Enter = (el) => {
      console.log('enter', el);
      gsap.to(el, {
        duration: 1,
        y: 0,
        opacity: 1,
        ease: "ease-in",
      });
    }
    const afterEnter = (el) => {
      console.log('after enter');
    }
    return { beforeEnter, Enter, afterEnter, showTitle }

  }
}

</script>

<style>
.about {
  max-width: 600px;
  margin: 20px auto;
  box-sizing: border-box;
  background-color: #F7F5F2;
  border-radius: 0.5rem;
}

.about h1 {
  color: #C65D7B;
  background-color: #57be80;
  padding: .5rem;
  border-top-left-radius: 0.5rem;
  border-top-right-radius: 0.5rem;
}

.about p {
  text-align: justify;
  padding: 1rem;
}
</style>