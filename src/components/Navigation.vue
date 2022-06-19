<template>
  <nav>
      <div class="nav-container">
          <h1>HELLBOUND</h1>
          <div class="main-nav">
                <div class="main-nav__button">
                    <span class="burguer-menu top"></span>
                    <span class="burguer-menu middle"></span>
                    <span class="burguer-menu bottom"></span>
              </div>
              
          </div>
      </div> 
  </nav>
</template>

<script>
export default {

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
    }

    .burguer-menu{
        width: 50px;
        height: 3px;
        background: #000;
        position: absolute;
    }

    .burguer-menu.top{
        top: 0;
    }

    .burguer-menu.middle{
        top: 6px;
    }
    .burguer-menu.bottom{
        top: 12px;
    }
</style>