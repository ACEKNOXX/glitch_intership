<template>
  <div>
       <div class="layer-1">
       

        <div class="row " style="margin-bottom:0px !important;">
            <div class="col s6 m6  h pink-1"></div>
            <div class="col s6 m6  h pink-2"></div> 
        </div>

        <!-- footer -->
            <footer class="page-footer pink-2" style="margin-top:-18px !important;">
            
            <div class="footer-copyright">
                <div class="container center grey-text">
                 Designed by @acekn(fluffydev)
                </div>
            </div>
            </footer>
        <!-- footer -->
    </div>
    <div class="layer-2" style="height:200px;">
        <div class="row">
            <div class="col s12 center">
                <h3 class="white-text" style="letter-spacing: 15px;">{{title}}</h3>
            </div>
        </div>
        <div class=" row " >
            <div class="col s12 m3"></div>
            <div class="col s12 m6">
                <div class="main-image "></div>
            </div>
            <div class="col s12 m3"></div>
        </div>
        <div class="row container center show-on-med-and-down hide-on-med-and-up " style="margin-top:-20px;">
            <div class="col  s12 m12">
                <div class="avatar center circle"></div>
            </div>
        </div>
        <div class="row container center hide-on-med-and-down ">
            <div class="col s12 m1"></div>
            <div class="col s12 m4">
                <div class="row">
                    <div class="col  s12 m6">
                        <a href="#">
                          <h6 class="grey-text text-lighten-5">HOME</h6>
                        </a>
                    </div>
                    <div class="col s12 m6">
                        <a href="#">
                          <h6 class="grey-text text-lighten-5">ABOUT</h6>
                        </a>
                    </div>
                </div>
            </div>
            <div class="col  s12 m2">
                <div class="avatar center circle"></div>
            </div>
             <div class="col s12 m4">
                <div class="row">
                    <div class="col  s12 m6">
                        <a href="#">
                          <h6 class="grey-text text-lighten-5">GALLERY</h6>
                        </a>
                    </div>
                    <div class="col s12 m6">
                        <a href="#">
                          <h6 class="grey-text text-lighten-5">CONTACT</h6>
                        </a>
                    </div>
                </div>
            </div>
            <div class="col s12 m1"></div>
        </div>
    </div>
    <div class="layer-3 " >
        <!-- Dropdown Trigger -->
      <a class='  btn-flat transparent  center white-text dropdown-trigger' href='#' data-target='dropdown1'>
        <i class="material-icons">menu</i>
      </a>

      <!-- Dropdown Structure -->
      <ul id='dropdown1' class='dropdown-content'>
        <li><a href="#!">HOME</a></li>
        <li><a href="#!">ABOUT</a></li>
        <li class="divider" tabindex="-1"></li>
        <li><a href="#!">GALLERY</a></li>
        <li><a href="#!">CONTACT</a></li>        
      </ul>
        
        <div class="row" style="margin-top:200px;">
            <div class="col s12 m5"></div>
            <div class="col s12 m6"></div>
            <div class="col s12  m1" style="height:200px;">
                <div class="row socials">
                    <div class="col s12">
                        <a v-bind:href="instagram">
                          <i class="right white-text fab fa-instagram fa-3x"></i>
                        </a>
                    </div>
                    <div class="col s12 ">
                      <a v-bind:href="twitter">
                        <i class="right white-text fab fa-twitter-square fa-3x"></i>
                      </a>
                    </div>
                    <div class="col s12">
                        <a v-bind:href="snapchat">
                          <i class="right white-text fab fa-snapchat-square fa-3x"></i>                        
                        </a>
                    </div>
                    <div class="col s12">
                        <a v-bind:href="'mailto:'+email">
                          <i class="right white-text fas fa-envelope-square fa-3x"></i>                      
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </div>
    
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "App",
  data() {
    return {
      title:  "AQUILA ",
      instagram:"#",
      twitter:"#",
      snapchat:"#",
      email:"#"
    };
  },
  async mounted(){
  
    try{
      const res = await axios.get("https://hirng-x2021.glitch.me/api");
      console.log(res.data.social_media.twitter);
      this.title = res.data.name;
      let tw="https://www.twitter.com/"+res.data.social_media.twitter;
      let snap="https://www.snapchat.com/"+res.data.social_media.snapchat;
      let mail = res.data.social_media.email;
      let ig="https://www.instagram.com/"+res.data.social_media.instagram
      this.instagram=ig;
      this.twitter=tw;
      this.snapchat=snap;
      this.email=mail;
    }catch(e){
      console.log(e);
    }
  }

};
</script>

<style scoped>

.bor{
  border:2px dashed red;
}
.h{
height:750px;
}
.pink-1{ background-color:#BD0F4D; }
.pink-2{background-color:#CB2964;}
.layer-1{
  position: absolute;
  left: 0px;
  top: 0px;
  z-index: -1;
  width:100% !important;
}
.layer-3,.layer-4{
  position: absolute;
  left: 0px;
  top: 0px;
  z-index: 2;
  width:100% !important;
}
.layer-5{
  position: absolute;
  left: 0px;
  top: 0px;
  z-index: 6;
  width:90% !important;
}
.main-image{
  background:url("~@/assets/3.jpg");
  background-color:#BD0F4D;
  background-repeat:no-repeat;
  background-size:cover;
  background-position:center ;
  height:450px;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19) !important;
  margin-bottom:50px;
}
.avatar{
  background:url("~@/assets/3.jpg");
  background-repeat:no-repeat;
  background-size:cover;
  background-position:center;
  margin:0px auto !important;
  margin-top:-20px !important;
  width:100px;height:100px;
}
.socials .s12{
  margin-bottom:20px;
}
</style>
