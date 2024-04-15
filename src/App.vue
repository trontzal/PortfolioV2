<template>

    <router-view class="routerView"/>

    <div id="navBar">
      <NavBarComp />
    </div>
    <div id="navBarPequeno">
      <NavBarPequeno/>
    </div>
  

</template>

<script>
  import NavBarComp from './components/NavBarComp.vue';
  import NavBarPequeno from '@/components/NavBarPequeno.vue';

  export default {
    components: {
      NavBarComp,
      NavBarPequeno
    }
  }
</script>

<style lang="scss">
  *{
    margin: 0;
  }
  #app {
    width: 100%;
    height: 100vh;
    height: 100vh;
    overflow: auto; 
    display: flex;
    font-family: Elianto;
  }

  #navBar {
    display: flex;
    align-items: center;
    margin-left: auto;
    margin-right: 1rem;
    width: 15%;
    justify-content: end;
    z-index: 1;
  }

  #navBarPequeno{
    background-color: rgb(0, 0, 0);
    position: fixed;
    bottom: 0;
    z-index: 100;
    width: 100%;
    height: 5rem;
    display: none;
    justify-content: space-between;
  }

  @media  screen and (max-width:768px) {
    #navBar{
      display: none;
    } 
    #navBarPequeno{
      display: flex;
    }  
  }
</style>
