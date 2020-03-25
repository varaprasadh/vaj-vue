
<template>
    <div class="prj-item" ref="prj_item">
        <div class="prj-tags">
            <span :key="tag" v-for="(tag,index) in data.tags" :class="['tag','color-'+(index%4)]">{{tag}}</span>

        </div>
        <div class="prj-title">{{data.title}}</div>
        <div class="prj-desc">
            {{data.description}}
        </div>
        <div class="prj-link">
            <a target="_blank" :href="data.link">source code ></a>
        </div>
    </div>
</template>
<script>

export default {
 name:"Project",
 props:["data"],
 created(){

 },
 mounted(){
       let item=this.$refs.prj_item;
        window.addEventListener('scroll', function(){
            let _top=item.getBoundingClientRect().top;
            let item_height=item.offsetHeight;
            let diff=_top-window.innerHeight+item_height/4;
            
            //when comes from top to bottom
            if(diff<0 && _top+item_height>=0){
                //do some
                item.classList.add('active');
                // console.log(diff);
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
.prj-item{
      background: rgb(255, 255, 255);
      margin: 0.2em;
      padding: 1em;
      border-radius: 5px;
      box-shadow: 1px 1px 1px rgba(0, 0, 0, 0.472);
      transform: translateX(-100%);
      transition: all 1s cubic-bezier(0.175, 0.885, 0.32, 1);
      display: flex;
      flex-direction: column;
   }
   .prj-item.active{
    transform: translateX(0%);

   }
    
   .prj-title{
       font-size: 1.7em;
       font-weight: bold;
       padding: 0.5em;
       color: rgb(44, 43, 43);
   }
   .prj-desc{
       padding: 1.2em 0.5em;
       color: rgb(90, 82, 82);
   }
   .prj-tags{
       display: flex;
       flex-wrap: wrap;
   }
   .prj-link{
       text-align: end;
       margin: 2em 0em 1em 0;
       margin-top: auto;
   }
   .prj-link a{
       text-decoration:none;
       color: rgb(1, 177, 1);
       padding: 0.5em 1em;
       border: 1px solid rgb(1, 177, 1);;
   }
    @media screen and (min-width:900px){
    .prj-item{
        flex-basis: 300px;
        max-width: 400px;
       
    }
    }

</style>