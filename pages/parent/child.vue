<template lang='pug'>
div.hijo
  h1 Child component: {{numero}}
    li
      nuxt-link(to='/parent/child/grandChild') Call grandchild
  nuxt-child(:numero='numero' @setParentText="event => $emit('setParentText', event)" @decrease='$emit(`decrease`)')
</template>

<script>
export default {
  props:['numero'],
  emits: ['decrease', 'setParentText'],
  data(){
    return{}
  }
}
</script>

<style>
.hijo{
  background-color: aqua;
}
</style>