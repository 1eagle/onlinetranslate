<template>
  <div id="app">
   <h1>在线翻译</h1>
   <h5>简单 / 快捷 /易用</h5>
   <Translate v-on:qq="textTranslate"></Translate>
   <outputabc v-text="translatedText"></outputabc>
  </div>
</template>

<script>
import Translate from "./components/translate"
import outputabc from "./components/outputabc"
export default {
  name: 'App',
  data:function(){
    return {
      translatedText:""
    }
  },
  components:{
    Translate,
    outputabc
  },
  methods:{
    textTranslate:function(x,la){
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180906T140648Z.eed9de8bb0306ded.404d6ccc1d8ef264eb56a9e8aae01af489ba2bda&lang='+la+'&text='+x).then((response)=>{
       this.translatedText=response.body.text[0]
      })
      
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
