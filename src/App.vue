<template>
  <NavBar></NavBar>
  <Card   :api-data="apiData.data"/>
</template>

<script>

import NavBar from "./components/NavBar.vue";

import Card from "./components/Card.vue";

export default {
  
 
  components: {
    NavBar,
    Card,
  },
 
  data:function(){
    return {apiData:[]}
  },
  methods: {
     getApi(num){
      fetch(`https://www.scoopwhoop.com/api/v4/read/all/?offset=0&limit=${num}`).then((response)=>{
      if(response.ok){
        return response.json()
        
      }
    }).then((data)=>{
        this.apiData = data;
       
    })
    },
      getNewData(newData) {
      window.onscroll = () => {
        let bottomOfWindow = document.documentElement.scrollTop + window.innerHeight == document.documentElement.offsetHeight;
        if (bottomOfWindow) {
         newData+=8
         this.getApi(newData)
         
        }
      }
    },
    
  },
  beforeMount() {
    this.getApi(8);
  },
  mounted() {
    this.getNewData(8);
  },
};

</script>

<style>
@font-face {
  font-family: 'Roboto';
  src: url('../src/assets/Fonts/Roboto-Regular.ttf');
}
body {
  font-size: 14px;
  font-weight: 700;
  letter-spacing: 0.03em;
  font-family: Roboto, sans-serif;
  margin: 0;
  padding: 0;
}


</style>
