<template>
<div>
  <child :sendChildData="sendChildData"/>
  <div>
  <h6>
  This is the value of your object in parent component :
{{calculationNumber}}
  </h6>
  </div>
  </div>
</template>

<script>
import Child from "./components/child.vue";
export default {
  name: "App",
  components: {
    Child: Child,
  },
  data(){
    return {
 calculationNumber:0
    }
  },
  methods:{
    sendChildData(number){
      this.calculationNumber = number
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
