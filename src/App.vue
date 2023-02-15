<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link to="/contact">Contact</router-link>
  </div>
  <router-view v-slot="{ Component }">
    <Transition name="route" mode="out-in">
      <component :is="Component"></component>
    </Transition>
  </router-view>
  <div class="footer">
    <div class="icons-footer">
      <img :src="path1" alt="instagram">
      <img :src="path2" alt="telegram">
      <img :src="path3" alt="linkedin">
    </div>

    <h4>©Design By Leili</h4>

    <div>
      <a href="#" class="btn-subscribe">Subscribe</a>
      <a href="#" class="btn-subscribe">Request</a>
    </div>

  </div>
</template>
<script>
export default {
  data(){
   return{
    path1 : require('../src/assets/instagram.png') ,
    path2 : require('../src/assets/telegram.png') ,
    path3 : require('../src/assets/linkedin.png') ,
   }
  }
}
</script>
<style>
body {
  font-family: 'Roboto Condensed', sans-serif;
  text-align: center;
  color: #2c3e50;
  margin: 0;
  background: #f2f2f2;
}
/* Nav */ 
#nav {
  display: block;
  padding: 30px 0;
  color: #57be80;
  background-color: #F7F5F2;
}
#nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  padding: 20px 30px;
}
#nav a.router-link-exact-active {
  color: #42b983;
}
/* Nav */ 

/* Route Transitions */
.route-enter-from {
  opacity: 0;
  transform: translateX(500px);
}
.route-enter-active {
  transition: all 0.3s ease-out;
}
.route-leave-to {
  opacity: 1;
  transform: translateX(-500px);
}
.route-leave-active {
  transition: all 0.3s ease-in;
}
/* Footer Section */
.footer {
  position: absolute;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  width: 100%;
  height: 100px;
  bottom: 0;
  background-color: #57be80;
}
.icons-footer img {
  padding: 5px;
}
.icons-footer img:hover{
  cursor: pointer;
}
/* Footer Section */

/* Buttons */
.btn-subscribe{
  background-color: transparent;
  width: 100%;
  font-weight: 700;
  font-size: .9rem;
  color: #ffff;
  border: 1px solid #ffff;
  padding: .8rem;
  margin: .5rem;
  border-radius: .3rem;
  transition: all .5s;
  text-decoration: none !important;
}
.btn-subscribe:hover{
  background-color: #ffff;
  color: #C65D7B;
  cursor: pointer;
}
/* Buttons */
</style>