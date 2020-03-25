<template>
     <div class="land-container">
         <div class="land_main_row">
            <div class="title-wrapper">
                <div class="title">
                    <div class="title-pre">Hi, I Am</div>
                    <div class="title-name">Varaprasadh</div>
                    <div class="title-name">Alajangi</div>
                    <div class="title-slogan">aspiring full stack developer & looking for opportunities!</div>
                </div>
                <div class="hl-buttons">
                    <a href="#know-more">
                        <div class="btn knowmore">Know More</div>
                    </a>
                </div>
            </div>
            <div class="dp-wrapper">
            <div class="dp-div">
                <img src="../images/dp_raw.png" alt="picture of varaprasadh">
            </div>
            </div>
         </div>

     </div>
</template>
<script>
export default {
    name:"LandingPage"
}
</script>
<style scoped>

.land-container{
    background: rgb(0, 0, 8);
    height: 100vh;
    width: 100vw;
    overflow: hidden;
}
.land_main_row{
    display: flex;
    flex-direction: column-reverse;
    align-items: center;
    padding: 2em;
}
.title-wrapper{
    flex: 1;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}
.title{
    color: white;
    font-weight: bold;
    font-family: sans-serif;
    font-size: 3em;
    transition: all 0.7s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}
.title-pre{
    font-size: .4em;
    filter: brightness(0.5);
    opacity:0;
   
}
.title-name{
    animation-delay: 1s;
    opacity: 0;
}
.title-slogan{
    font-size: 0.3em;
    color: rgb(84, 177, 84);
    opacity: 0;
    margin-top: 10px;
}
.dp-wrapper{
    flex: 1;
    padding: 1em;
    display: flex;
    justify-content: start;
}
.dp-div{
  position: relative;  
  padding: 1em;
}
.dp-div img{
    width:250px;
    height: auto;
    border-radius: 50%;
    object-fit: contain;
    box-shadow: 0.15em 0.15em 0.4em rgb(53, 198, 255),
                -0.15em -0.15em 0.4em rgb(42, 241, 191);
    opacity: 0;
  }
  .hl-buttons{
      display: flex;
      margin: 1em;
    
  }
  .btn, .btn:focus{
      padding: 0.5em 1em;
      color: white;
      font-weight: bold;
      font-family: sans-serif;
      margin: 1em;
      font-size: 1.2em;
      opacity: 0;
      border-radius: 0.5em;
      cursor: pointer;
      transition: all 0.2s ease-in-out;
      text-align: center;
      user-select: none;
  }
  .btn:hover{
      filter: brightness(0.6);
  }
  .btn.hireme{
        background: green;
        
    }
  .btn.knowmore{
        background: rgb(23, 69, 219);
    }
   .loaded .title-pre{
     animation: fadeUp 1s cubic-bezier(0.175, 0.885, 0.32, 1.275) 1;
     animation-fill-mode:forwards;
   }
    .loaded .title-name{
     animation: fadeUp 1s cubic-bezier(0.175, 0.885, 0.32, 1.275) 1s 1;
     animation-fill-mode:forwards;
    }
   .loaded .dp-div img{
    animation: fadeLeft 2s cubic-bezier(0.175, 0.885, 0.32, 1.275) 1;
    animation-delay: 1.5s;
    animation-fill-mode:forwards;
   }
   .loaded .btn, .btn:focus{
    animation: fadeUp 1s cubic-bezier(0.175, 0.885, 0.32, 1.275) 2s 1;
    animation-fill-mode:forwards;
   }
   .loaded .title-slogan{
    animation: fadeLeft 1s cubic-bezier(0.175, 0.885, 0.32, 1.275) 2s 1;
    animation-fill-mode:forwards;
   }
  

@keyframes fadeUp {
    0%{
        transform: translateY(200px);
        opacity: 0;
    }
    100%{
        transform: translateY(0px);
        opacity: 1;
    }
}
@keyframes fadeLeft {
    0%{
        transform: translateX(400px);
        opacity: 0;
    }
    100%{
        transform: translateX(0px);
        opacity: 1;
    }
}
@media screen and (min-width:1000px) {
    .land-container{
        display: flex;
        flex-direction: column;
        justify-content: center;
        font-size: 20px;
    }
    .title{
        font-size: 4em;
    }
    .dp-div img{
        width: 20em;
    }
   .land_main_row{
    flex-direction: row;
    align-items: center;
    padding: 3em;
    justify-content: center;
  }
}
@media screen and (min-width:1200px) {
   .dp-div img{
        width: 500px;
    }
}


</style>