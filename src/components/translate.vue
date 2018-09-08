<template>
  <div id="translate">
   <form v-on:submit="formSubmit">
       <input type="text" v-model="tcontent" placeholder="please input something">
       <select v-model="la">
           <option value="en">English</option>
           <option value="ru">Russion</option>
           <option value="ko">Korean</option>
           <option value="ja">Janpanese</option>
       </select>
       <input type="submit" value="translate">
   </form>
  </div>
</template>

<script>
export default {
  name: 'translate',
  data:function(){
      return {
          tcontent:"",
          la:"en"
      }
  },
  methods:{
      formSubmit:function(e){
       this.$emit("qq",this.tcontent,this.la);
      e.preventDefault();
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
