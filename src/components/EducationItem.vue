<template>
    <div class="te-wrapper">
        <div class="te-img">
            <img v-if="data.img==='backpack'" src="../images/backpack.svg" alt="ssc logo">
            <img v-if="data.img=='mechanic'" src="../images/mechanic.svg" alt="ssc logo">
            <img v-if="data.img=='browser'" src="../images/browser.svg" alt="ssc logo">
            <img v-if="data.img=='school'" src="../images/school.svg" alt="ssc logo">
        </div>
        <div class="te-content">
            <div class="edu-title">{{data.title}}</div>
            <div class="edu-where">at {{data.where}}</div>
            <div class="edu-when">on year {{data.when}}</div>
            <div class="edu-score">
                <span>with {{data.grade}}</span>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props:["data"]
}
</script>
<style scoped>
 .te-wrapper{
     display: flex;
     align-items: center;
     font-weight: bold;
     font-family: sans-serif;
     padding: 0.5em;
     margin-left: 1.5em;
 }

 .edu-title{
     font-size: 1.2em;
     color: rgb(94, 89, 89);
 }
 .edu-where{
     color: rgb(140, 55, 209);
 }
 .edu-when{
     color: rgb(115, 111, 119);
 }
 .te-content{
     flex: 1;
 }
 .te-content>*{
     margin-bottom: 0.5em;
     padding: 0.2em 0.4em;
 }
 .edu-score{
     color: white;
     display: flex;
     justify-content: flex-end;
 }
  .edu-score span{
      background: rgb(255, 152, 33);
      padding: 0.3em 1em;
      display: block;
      border-radius: 5px;
  }
 .te-img img{
     height: 100px;
     width:100px;
 }
</style>