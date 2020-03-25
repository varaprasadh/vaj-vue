<template>
  <div id="app">
    <transition appear name="load" :duration="{ enter: 1000, leave: 2000 }">
        <Loader v-if="!loaded"/>
    </transition>
    <LandingPage/>
    <About/>
    <Projects/> 
    <Education/>
    <TechStack/> 
    <ContactMe/> 
    <div class="footer">
      <div class="copyright">varaprasadhaj | 2k20</div>
    </div>
  </div>
</template>

<script>
import LandingPage from "./components/LandingPage";
import About from "./components/AboutMe";
import Projects from "./components/Projects";
import Education from "./components/Education";
import TechStack from "./components/TechStack";
import ContactMe from "./components/ContactMe";
import Loader from "./components/Loader";
export default {
  name: 'App',
  data:()=>({
    loaded:false
  }),
  components: {
    LandingPage,
    About,
    Projects,
    Education,
    TechStack,
    ContactMe,
    Loader
  },
  mounted(){
    window.onload=()=>{
      setTimeout(()=>{
        this.loaded=true;
      },1000);
      setTimeout(() => {
        document.querySelector('#app').classList.add('loaded');
      }, 2000);
    }
  }
}
</script>

<style>
html,body{
  padding: 0;
  margin: 0;
  font-family: sans-serif;
  overflow-x: hidden;
  scroll-behavior: smooth;
}
  .sec-title{
       font-weight: bold;
       font-size: 2em;
       padding: 0.5em;
       color: rgb(83, 76, 76);
   }
   a{
     text-decoration: none;
   }
   .tag{
       background: rgb(162, 180, 2);
       color: white;
       display: inline-block;
       padding: 0.2em;
       font-size: 0.7em;
       margin: 2px 2px;
   }
    .color-0{
       background: rgb(162, 180, 2);
   }
   .color-1{
       background: rgb(211, 114, 3);
   }
   .color-2{
       background: rgb(141, 4, 165);
   }
   .color-3{
       background: rgb(128, 4, 55);
   }
   .footer{
     background: rgb(6, 3, 32);
     color: white;
     padding: 1em;
     text-align: center;
     font-weight: bold;
   }

</style>
