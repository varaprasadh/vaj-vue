<template>
    <div class="prj-container">
        <a name="projects"></a>
        <div class="sec-title">
            projects i did,
        </div>
        <div class="prj-list">
            <ProjectItem :key="prj.id" v-for="prj in projects" :data="prj"/>
        </div>
    </div>
</template>
<script>
import ProjectItem from "./ProjectItem";
export default {
    name:"Projects",
    components:{
        ProjectItem
    },
    created(){
      const data=require('../data/projects.json');
      this.projects=data.projects;
    },
    data:()=>({
        projects:[]
    })
}
</script>

<style  scoped>
   .prj-container{
     background: rgb(238, 237, 234);
     font-family: sans-serif;
   }
 
   .prj-list{
    padding: 10px;
    display: flex;
    width:100vw;
    flex-direction: column;
    box-sizing: border-box;
   }
    @media screen and (min-width:900px){
    .prj-list{
       display: flex;
       flex-direction: row;
       flex-wrap: wrap;
       justify-content: center;
      }
    }
</style>
