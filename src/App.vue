<template>
  <div id="app">
  <navTop/>
  <userBox/>
  <aD/>
  <schoolCard/>
  <schoolTraffic/>
  <uniComponent/>
  </div>
</template>
<script>
import navTop from './components/navTop.vue';
import userBox from './components/userBox';
import aD from './components/aD.vue';
import schoolCard from './components/shcoolCard.vue'
import schoolTraffic from './components/schoolTraffic.vue'
import uniComponent from './components/uniComponent.vue';
export default{
    components: { 
      navTop,
      userBox,
      aD,
      schoolCard,
      schoolTraffic,
      uniComponent
    }
}
</script>
<style>
  *{
    user-select: none;
    margin: 0;
    padding: 0;
    outline:none;
    border: 0;
  }
  #app{
    background-color: rgb(248, 249, 253);
  }
</style>