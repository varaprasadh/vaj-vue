<template>
        <div class="loader">
            <div class="loader-box">
                <span class="_tag _tag1"> &lt; </span>
                <span class="_tag _tag2"> /</span>
                <span class="_tag _tag3"> &gt; </span>
                <div class="load-info">loading ...</div>
            </div>
        </div>
</template>
<script>
export default {
    name:"Loader"
}
</script>
<style scoped>
.loader{
    position: fixed;
    top: 0px;
    left: 0px;
    width: 100vw;
    height: 100vh;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
    color: gray;
    background: black;
    z-index: 100;
}
.loader-box{
    text-align: center;
}
._tag{
   display: inline-block;
   margin:10px;
   font-size: 2em;
}
._tag1{
    animation: slide_l 1s cubic-bezier(0.165, 0.84, 0.44, 1) 2s infinite alternate;
}
._tag3{
    animation: slide_r 1s cubic-bezier(0.165, 0.84, 0.44, 1) 2s infinite alternate;
}

.load-enter-active ._tag,
.load-enter-active .load-info,
.load-leave-active ._tag{
    transition: all 1s cubic-bezier(0.455, 0.03, 0.515, 0.955);
}
.load-enter .load-info{
    opacity: 0;
}
.load-enter ._tag1{
  transform: translateX(-500px);
  opacity: 0;
}
.load-enter ._tag3{
  transform: translateX(500px);
  opacity: 0;
}
.load-leave-to .load-info{
    opacity: 0;
}
.load-leave-to ._tag1{
  transform: translateX(-500px);
  opacity: 0;
}
.load-leave-to ._tag3{
  transform: translateX(500px);
  opacity: 0;
}
.load-leave-to ._tag2{
    transform:translateY(1000px);
}

@keyframes pulse {
   to{
       transform: scale(1.2);
   }
}
@keyframes slide_l {
   to{
       transform: translateX(-20px);
   }
}
@keyframes slide_r {
   to{
       transform: translateX(20px);
   }
}

</style>