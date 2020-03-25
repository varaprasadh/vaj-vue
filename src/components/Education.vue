<template>
    <div class="edu-container">
        <div class="sec-title">what i studied,</div>
        <div class="timeline" ref="edu_timeline">
            <div  class="timeline-element">
                <EducationItem :data="edu[0]"/>
            </div>
            <div  class="timeline-element">
                <EducationItem :data="edu[1]"/>
            </div>
            <div  class="timeline-element">
                <EducationItem :data="edu[2]"/>
            </div>
            <div  class="timeline-element">
                <EducationItem :data="edu[3]"/>
            </div>
        </div>
    </div>
</template>
<script>
import EducationItem from "./EducationItem";
export default {
    name:"Education",
    components:{
        EducationItem
    },
    data:()=>({
      edu:[ {
          title:"Computer Science Engineering",
          where:"Anits",
          when:'2020',
          grade:"7.2 GPA",
          img:'browser'
      },{
          title:"Diploma in Mechanical Engineering",
          where:"Govt.Polytechnic,sklm",
          when:"2017",
          grade:"90%",
          img:'mechanic'
      },
      {
          title:"Secondary School Education",
          where:"Maharshi high School",
          when:"2014",
          grade:"9.2 GPA",
          img:'backpack'
      },
      {
          title:"Elementary School Education",
          where:"MPUP School",
          when:"2009",
          grade:"N/A",
          img:'school'
      }
     ]
    }),
     mounted(){
       let item=this.$refs.edu_timeline;
        window.addEventListener('scroll', function(){
            let _top=item.getBoundingClientRect().top;
            let item_height=item.offsetHeight;
            let diff=_top-window.innerHeight+item_height/2;
            
            //when comes from top to bottom
            if(diff<0 && _top+item_height>=0){
                //do some
                item.classList.add('active');
            }
            else{
                item.classList.remove('active');
            }
        });
 },
 destroyed () {
    window.removeEventListener('scroll',()=>{});
  }
}
</script>
<style scoped>
.temp{
    height: 1000px;
}

 .timeline-element{
     position: relative;
     margin: 10px 0;
 }

 .timeline.active .timeline-element::after{
    position: absolute;
    content: '';
    display: block;
    width:10px;
    height: 0%;
    top:0;
    margin: 0px 0.6em;
    z-index: -1;
    animation: grow 0.5s cubic-bezier(0.445, 0.05, 0.55, 0.95) 1;
    animation-fill-mode:forwards;
 }
 .timeline.active .timeline-element:nth-child(1)::after{
     animation-delay: 0s;
     background: rgb(20, 255, 137);
 }
 .timeline.active .timeline-element:nth-child(2)::after{
     animation-delay: 1s;
     background: rgb(90, 60, 223);
 }
 .timeline.active .timeline-element:nth-child(3)::after{
     animation-delay: 1.5s;
     background: rgb(230, 94, 4);
 }
 .timeline.active .timeline-element:nth-child(4)::after{
     animation-delay: 2s;
     background: rgb(170, 18, 124);
 }
 @keyframes  grow {
     0%{
         height: 0%;
     }
     100%{
         height: 100%;
     }
 }
  @media screen and (min-width:900px){
    .timeline{
        display: grid;
        grid-template-columns: 1fr 1fr;
    }
    }

</style>