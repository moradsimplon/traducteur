<template>
  <div id="app">
  <entete></entete>
  <traduc  v-on:recup='trad'></traduc>
  <affichage :someData="someData"></affichage>
  </div>
</template>

<script>
import entete from './components/entete'
import traduc from './components/traduc'
import affichage from './components/affichage'

export default {
  name: 'app',
  components: {
    entete,
    traduc,
    affichage
  },




      data(){
        return{
          someData:''
        }
      },

        methods : {
          trad : function(word,langue){
          console.log(word);
          // GET /someUrl
          this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20170830T082407Z.f8116e82af63c91e.41d29f1e8b9f032a4b0f6d79025988d262e75296&lang=fr-'+langue+'&text='+word).then(response => {
            // get body data
            this.someData = response.body.text[0];



          }, response => {
            // error callback
            console.log(word);
          });

        }
        }

    }


</script>

<style>

</style>
