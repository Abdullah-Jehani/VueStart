<template>
<div>{{greet}} {{name}}</div>
<button :disabled="isDisabled">Bind</button>
<h2 :class="status">underlined Text</h2>
<h2 :class="isPromoted ? 'promoted' : ''">Promoted Movie</h2> 
<h2 :class="isSoldout ? 'sold-out' : 'new'">Movie </h2> 
<h2 :class="['new' , 'promoted']">Newly Promoted Movie</h2>
<h2 :class="[isPromoted && 'promoted' , isSoldout ? 'sold-out' : 'new']">Array Condational movie</h2>
<h2 :class="{
  promoted: isPromoted , 
  'new': !isSoldout , 
  'sold-out': isSoldout
}">object condational Movie
</h2>
<h2 :style="{
  color: color , 
  'font-size' : fontSize + 'px' , 
  margin: 0  
}">Highlited Text</h2>
<!-- Apply Number of styling -->
<h2 :style="cssStyling">Style Object </h2> 
</template>
<script>
export default{
  name: 'App' , 
  data() {
    return {
      name: 'osama' ,
      greet : 'hello' ,
      isDisabled: true , 
      status: 'Success' , 
      isPromoted: true , 
      isSoldout: false ,
      color: 'gray' , 
      fontSize: 50 , 
      cssStyling: {
        color: 'yellow' , 
        fontSize: '30px' , 
        

      }
    } ;
  },
  methods: {
  
  }
 
} ;
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
.underlined {
  text-decoration: underline;
}
.Success {
  color: red;
} 
.promoted {
  font-style: italic;
  color: orange; 
  
}
.sold-out {
  color: red;
} 
.new {
  color: green;
}
</style>
