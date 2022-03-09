<template>
  <div class="hijo">
    <h1>Child component: {{numero}} </h1>
    <h2>Name: {{nombre}}</h2>
    <li>
      <NuxtLink to="/parent/child/grandChild">Call grandchild</NuxtLink>
    </li>
    <NuxtChild :numero='numeroPadre' />
  </div>
</template>

<script>
export default {
  props:['numero'],
  data(){
    return{
      nombre: 'Christian',
      numeroPadre: 0
    }
  },
  mounted(){
    this.$emit('nombreHijo', this.nombre);
  }

}
</script>

<style>
.hijo{
  background-color: aqua;
}
</style>