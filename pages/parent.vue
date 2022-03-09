<template>
  <div>
    <h1 class="title">Item counter</h1>
    <div class="padre">
      <h1>Father component: {{ numeroPadre }}</h1>
      <b-button type="is-primary" @click="numeroPadre++">+</b-button>
      <li>
        <NuxtLink to="/parent/child">Call Child</NuxtLink>
      </li>
      <h1>{{ nombrePadre }}</h1>
      <NuxtChild :numero="numeroPadre" @nombreHijo="nombrePadre = $event" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numeroPadre: 0,
      nombrePadre: "",
    };
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