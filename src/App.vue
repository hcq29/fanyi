<template>
  <div id="app">
    <h1>29在线翻译</h1>
      <h5 class="text-muted">简单 / 易用 / 便捷</h5>
    <translateFrom v-on:formSubmit="translateText"></translateFrom>
    <translateOutput v-text="translatedText"></translateOutput>
  </div>
</template>

<script>
import translateFrom from './components/translateFrom'
import translateOutput from './components/translateOutput'

export default {
  name: 'App',
  data: function(){
    return {
      translatedText: ""
    }
  },
  methods:{
    translateText: function(text,lang){
      console.log(text);
      console.log(lang);
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20191230T065805Z.579a3300bd80235c.59067d8d383c6f2bc003dc03d728f01c768a75ba&lang=' + lang + '&text=' + text).then((response)=>{
        this.translatedText = response.body.text[0];
      });
    }
  },
  components: {
    translateFrom,
    translateOutput
  }
}
</script>

<style>
@import url("../src/assets/bootstrap.min.css");
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
