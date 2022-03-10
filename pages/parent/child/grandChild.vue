<template lang='pug'>
  div.nieto
    h1 Grandchild Component: {{numero}}
    b-button(type="is-danger" @click='$emit("decrease")') -
    input(type='text' @input="event => $emit('setParentText', event.target.value)")
</template>
<script>
export default {
  props:['numero'],
  emits: ['decrease', 'setParentText'],
  data(){
    return{
    }
  },
}
  
</script>

<style>
.nieto{
  background-color: rgb(236, 16, 16);
  color: black;
}
</style>