<template>
  <nav>
      <div class="nav-container">
          <h1>HELLBOUND</h1>
          <div class="main-nav">
                <div class="main-nav__button" @click="toggleActive()" :class="isActive ? 'active' : ''">
                    <span class="burguer-menu top"></span>
                    <span class="burguer-menu middle"></span>
                    <span class="burguer-menu bottom"></span>
              </div>
              
          </div>
      </div> 
  </nav>

  <div class="main-menu" :class="isActive ? 'active' : ''">
      <h1>Our Social Media</h1>
      <ul class="social-nav">
          
          <li><a href="https://www.youtube.com/hellboundshow" target="_blank"><font-awesome-icon icon="fa-brands fa-youtube" size="4x"/></a></li>
          <li><a href="https://www.facebook.com/hellbound.us" target="_blank"><font-awesome-icon icon="fa-brands fa-facebook" size="4x"/></a></li>
          <li><a href="https://www.instagram.com/hellboundshow/?hl=en" target="_blank"><font-awesome-icon icon="fa-brands fa-instagram" size="4x"/></a></li>
          <li><a href="https://www.patreon.com/HellboundShow" target="_blank"><font-awesome-icon icon="fa-brands fa-patreon" size="4x"/></a></li>
      </ul>
  </div>
</template>

<script>



export default {

    data(){
        return{
            isActive: false
        }
    },
    methods:{
        toggleActive(){
            console.log('toggling')
            this.isActive = !this.isActive
        }
    }

}
</script>

<style>
    nav{
        height: 100px;
        background: #EEB76B;
        display: flex;
        justify-items: center;
        border-bottom: 3px solid #310B0B;
        box-sizing: border-box;
        position: relative;
        z-index: 10;
    }

    nav .nav-container{
        max-width: 800px;
        margin: 0 auto;
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: space-between;
        justify-items: center;
    }

    nav h1{
        padding: 0;
        margin: 0 !important;
        color: #000;
        font-size: 3em;
        font-family: 'League Gothic', sans-serif;
    }

    .main-nav{
        display: block;
        position: relative;
        height: 15px;
        width: 50px;
    }

    .main-nav__button{
        position: relative;
        display: block;
        height: 15px;
    }

    .burguer-menu{
        width: 50px;
        height: 3px;
        background: #000;
        position: absolute;
        transition: all ease 0.2s;
    }

    .burguer-menu.top{
        top: 0;
        left: 0;
        transform-origin: center;
    }

    .burguer-menu.middle{
        top: 6px;
        left: 0;
        transform-origin: center;
    }
    .burguer-menu.bottom{
        top: 12px;
        left: 0;
        transform-origin: center;
    }

    .main-nav__button.active .burguer-menu.top{
        transform: rotate(45deg);
        top: 6px
    }

    .main-nav__button.active .burguer-menu.middle{
        transform: rotate(45deg);
    }

    .main-nav__button.active .burguer-menu.bottom{
        transform: rotate(-45deg);
        top: 6px;
    }

    .main-nav__button.active:before{
        content: '';
        position: absolute;
        height: 18px;
        width: 18px;
        /* border: 3px solid #000; */
        border-radius: 50%;
        top: -2px;
        left: 16px;
        background: #EEB76B;
        z-index: 5;
    }

    .main-nav__button.active:after{
        content: '';
        position: absolute;
        height: 25px;
        width: 25px;
        border: 3px solid #000;
        border-radius: 50%;
        top: -8px;
        left: 10px;
        background: transparent;
    }



    .main-menu{
        display: block;
        position: fixed;
        width: 100%;
        height: 100vh;
        background-color: #EEB76B;
        top: -100vh;
        padding-top: 0px;
        transition: all 0.5s;
        z-index: 5;
    }

    .main-menu.active{
        top: 0px;
        padding-top: 100px;
    }

    .main-menu h1{
        color: #000;
        text-decoration: underline;
    }

    .social-nav{
        padding: 0;
    }

    .social-nav li{
        display: inline-block;
        list-style: none;
        padding-left: 4rem;
        position: relative;
    }

    .social-nav li:hover svg.svg-inline--fa{
        color: #9C3D54

    }

    .social-nav li:first-child{
        padding-left: 0;
    }

    svg.svg-inline--fa{
        color: #000;
        transition: 0.3s;
    }
    
    @media only screen and (max-width: 600px) {
        nav{
            padding: 0 1rem;
        }

        .social-nav li{
            padding-left: 10px;
        }
        
    }

</style>