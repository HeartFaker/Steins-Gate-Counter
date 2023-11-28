<script>
import SteinsCounter from '../components/SteinsCounter.vue';
export default{
  components:{
    SteinsCounter,
  },
  data(){
    return{
      currentTime: new Date().toLocaleTimeString(),
      steinsGate:"1048596"
    }
  },
}
</script>

<template>
  <main>
    <SteinsCounter :DigitsString="steinsGate"/>
  </main>
</template>

<style scoped>

</style>
