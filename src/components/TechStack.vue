<template>
    <div class="tech-cotainer">
       <div class="sec-title">Technologies i worked on,</div>
       <div class="tsi-items">
            <TechStackItem :key="i" v-for="(ts,i) in tsi" :data="ts"/>
       </div>
       <div class="others">
           <div class="sec-title">of course i know,</div>
           <div class="tech-others">
               <div :key="i" v-for="(item,i) in langs" :class="['ot-item','color-'+i%4]">{{item}}</div>
           </div>
       </div>
    </div>
</template>
<script>
import TechStackItem from "./TechStackItem";
export default {
    name:"TechStack",
    components:{
        TechStackItem
    },
    data:()=>({
        tsi:[{
            tags:['web','desktop','js'],
            image:require('../images/tech/nodejs.svg'),
            title:"Node.Js"
        },
        {
            tags:['web','desktop','js'],
            image:require('../images/tech/reactjs.png'),
            title:"React.Js"
        },
        {
            tags:['web','desktop','js'],
            image:require('../images/tech/js.png'),
            title:"javascript"
        },
        {
            tags:['web','desktop','js'],
            image:require('../images/tech/chrome.png'),
            title:"chrome extensions"
        },
        {
            tags:['web','desktop','js'],
            image:require('../images/tech/vuejs.png'),
            title:"Vue.js"
        },
        {
            tags:['web','desktop','js'],
            image:require('../images/tech/electronjs.png'),
            title:"Electron.js"
        },
        {
            tags:['web','desktop','js'],
            image:require('../images/tech/reactjs.png'),
            title:"React Native"
        },{
            tags:['web','desktop','js'],
            image:require('../images/tech/mongodb.png'),
            title:"MongoDB"
        }],
        langs:["","Java","Python","C","GitHub","Android","MySQL","Express.js","html","css",""]
    })
}
</script>
<style scoped>
.tech-cotainer{
    background: #e8f0f5;
}
  .tsi-items{
      display: grid;
      grid-template-columns: 1fr 1fr;
  }
  .others{
      background: #ffffff;
  }
  .tech-others{
      display: flex;
      flex-wrap: wrap;
      padding: 0.5em;
      justify-content: space-around;
  }
  .ot-item{
      padding: 0.5em 1em;
      margin: 10px 10px;
      color: white;
      animation: jiggle 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275) infinite;
  }
  @keyframes jiggle {
      0%{
         transform: rotate(0deg);
      }
      50%{
         transform: rotate(-5deg);
      }
      75%{
         transform: rotate(0deg);
      }
      100%{
         transform: rotate(5deg);
      }
  }
  @media screen and (min-width:900px){
    .tsi-items{
      display: grid;
      grid-template-columns: 1fr 1fr 1fr;
    }
  }
  @media screen and (min-width:1200px){
    .tsi-items{
      display: grid;
      grid-template-columns: 1fr 1fr 1fr 1fr;
    }
  }


</style>
