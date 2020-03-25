<template>
    <div class="tsi-container" ref="tsi_item">
        <div class="tags">
            <span :key="index" v-for="(tag,index) in data.tags" :class="['tag','color-'+(index%4)]">{{tag}}</span>
        </div>
        <div class="tsi-main">
            <div class="tsi-img">
                <img :src="data.image" alt="image for the technology">
                <div class="tsi-lable">{{data.title}}</div>
            </div>
        </div>
    </div>
</template>
<script>

export default {
    props:["data"],
     mounted(){
       let item=this.$refs.tsi_item;
        window.addEventListener('scroll', function(){
            let _top=item.getBoundingClientRect().top;
            let item_height=item.offsetHeight;
            let diff=_top-window.innerHeight+item_height/2;
            
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
.tsi-container{
    padding:10px;
    background: white;
    box-shadow: 2px 2px 5px rgb(218, 243, 243);
    margin: 10px;
    border-radius: 10px;
    transform:scale(0);
    transition: all 0.7s cubic-bezier(0.175, 0.885, 0.32, 1);
}
.tsi-container.active{
    transform: scale(1);
}
.tsi-main{
    text-align: center;
}

.tsi-img img{
    width: 100px;
    height: 100px;
}
.tsi-lable{
    color: rgb(61, 46, 46);
    font-size: 1.2em;
    font-weight: bold;
}

</style>
