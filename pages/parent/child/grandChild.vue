<template lang='pug'>
  div.nieto
    h1 Grandchild Component: {{numero}}
    h2 Name: {{nombre1}}

  
</template>
<script>
export default {
  props:['numero'], 
  data(){
    return{
      nombre1:'Luis'
    }
  }
}
  
</script>

<style>
.nieto{
  background-color: rgb(236, 16, 16);
  color: black;
}
</style>