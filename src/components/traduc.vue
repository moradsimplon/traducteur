<template>





  <form v-on:submit='recup'class="container ">

  <select class="mdb-select" v-model='langue'>
      <option value="" disabled selected>Choisir la langue</option>
      <option value="en">Anglais</option>
      <option value="es">Espagnole</option>
      <option value="il">Italien</option>
      <option value="de">Allemand</option>

  </select>
  <label></label>

  <div class="md-form">
      <input type="text" id="form1" class="form-control" v-model="word" >
    
  </div>
  <button type="submit"  class="btn btn-outline-primary waves-effect">Traduire</button>
</form>




</template>

<script>
export default {
name : 'traduc',

data(){
  return {
    word: '',
    langue:''
  }
},
methods: {
  recup(obj){
    this.$emit('recup',this.word,this.langue)
    obj.preventDefault()
  }
}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
select{
  border-color: #0275d8;
  padding:3px;
  margin: 0;
  -webkit-border-radius:4px;
  -moz-border-radius:4px;
  border-radius:4px;
  /*-webkit-box-shadow: 0 3px 0 #ccc, 0 -1px #fff inset;*/
  /*-moz-box-shadow: 0 3px 0 #ccc, 0 -1px #fff inset;*/
  /*box-shadow: 0 3px 0 #ccc, 0 -1px #fff inset;*/
  background: white;
  color:rgb(13,71,161);

  /*outline:none;*/
  display: inline-block;
  -webkit-appearance:none;
  -moz-appearance:none;
  appearance:none;
  cursor:pointer;
}
</style>
