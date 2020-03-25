<template>
    <div class="cm-container">
        <div class="sec-title">Contact me through,</div>
        <div class="cm-wrapper">
            <a href="mailto:varaprasadh.a@gmail.com?Subject=hi%20from%20portfolio%20visitor">
                <div class="cm-item red">
                    <div class="cm-img">
                        <img src="../images/network/gmail.svg" alt="gmail">
                    </div>
                    <div class="cm-label">Send An Email</div>
                </div>
            </a>
            <a href="tel:+918106492369">
                <div class="cm-item phone">
                    <div class="cm-img ">
                        <img src="../images/network/phone.svg" alt="gmail">
                    </div>
                    <div class="cm-label">Make a Call</div>
                </div>
            </a>
            <a href="https://www.linkedin.com/in/varaprasadh-alajangi-a990b314b/" target="_blank">
                <div class="cm-item blue">
                    <div class="cm-img">
                        <img src="../images/network/linkedin.svg" alt="gmail">
                    </div>
                    <div class="cm-label">Visit My Profile</div>
                </div>
            </a>
            <a href="https://github.com/varaprasadh" target="_blank">
                <div class="cm-item black">
                    <div class="cm-img">
                        <img src="../images/network/github.svg" alt="gmail">
                    </div>
                    <div class="cm-label">GitHub</div>
                </div>
            </a>
            <a href="https://www.instagram.com/consious_coder/" target="_blank">
                <div class="cm-item insta">
                    <div class="cm-img">
                        <img src="../images/network/instagram.svg" alt="gmail">
                    </div>
                    <div class="cm-label">Follow me on Instagam</div>
                </div>
            </a>
        </div>
    </div>
</template>
<script>
export default {
    name:"Contact"
}
</script>
<style scoped>
.cm-container{
    background: #edf3f8;
}
.cm-container::before{
    content: '';
    display: block;
    height: 3px;
    margin: auto;
    background: rgb(172, 170, 170);
}
.cm-wrapper{
    display: flex;
    flex-direction: column;
    /* align-items: center; */
}
.cm-item{
    display: flex;
    align-items: center;
    /* justify-content: center; */
    padding:0.4em 1em;
    color: white;
    cursor: pointer;
    border-radius: 10px;
    margin: 10px;
    font-weight: bold;
    font-size: 1.2em;
    user-select: none;
}
a{
    text-decoration: none;
}
 .cm-img img{
     width: 50px;
     height: 50px;
     margin: 0 10px;
 }
 .cm-item.red{
     background: rgb(219, 28, 28);
 }
 .cm-item.blue{
     background: rgb(2, 105, 201);
 }
 .cm-item.black{
     background: rgb(12, 11, 11);
 }
 .cm-item.insta{
     background: linear-gradient(45deg,rgb(230, 67, 3),rgb(255, 28, 179));
 }
 .cm-item.phone{
     background: rgb(26, 7, 77);
 }
 .cm-item:hover{
     filter: brightness(0.7);
 }

   @media screen and (min-width:900px){
   .cm-wrapper{
       flex-direction: row;
       flex-wrap: wrap;
       align-items: center;
       justify-content: center;
}
  }

</style>