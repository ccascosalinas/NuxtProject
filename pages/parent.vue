<template lang='pug'>
div
  h1.title Item counter
  .padre
    h1 Father component: {{ numeroPadre }}
    p {{ text }}
    b-button(type='is-primary' @click='numeroPadre++') +
    li
      nuxt-link(to='/parent/child') Call Child
    nuxt-child(:numero='numeroPadre' @setParentText="setText" @decrease="decrease" ) 
</template>

<script>
export default {
  data() {
    return {
      numeroPadre: 0,
      text: ''
    };
  }, methods: {
    decrease() {
      this.numeroPadre--;
    },
    setText(value) {
      this.text = value;
    }
  }
};
</script>

<style>
.padre {
  background-color: chartreuse;
}
.title{
  text-align: center;
  font-size: 40px;
}
</style>          