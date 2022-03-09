<template>
  <div>
    <b-navbar>
      <template #brand>
        <b-navbar-item>
          <img
            src="https://www.islabit.com/wp-content/uploads/2021/11/agregar-notas-reunion-Docs.png"
          />
        </b-navbar-item>
      </template>
      <template #start>
        <b-navbar-item>
          <NuxtLink to="/">Home page</NuxtLink>
        </b-navbar-item>
        <b-navbar-item>
          <NuxtLink to="/inspire">Inspire</NuxtLink>
        </b-navbar-item>
        <b-navbar-item>
          <NuxtLink to="/about">About</NuxtLink>
        </b-navbar-item>
        <b-navbar-item >
          <NuxtLink to="/parent">Parent</NuxtLink>
        </b-navbar-item>
      </template>

      <template #end>
        <b-navbar-item tag="div">
          <div class="buttons">
            <a class="button is-primary">
              <strong>Sign up</strong>
            </a>
            <a class="button is-light"> Log in </a>
          </div>
        </b-navbar-item>
      </template>
    </b-navbar>
    <Nuxt />
  </div>
</template>

<script>
export default {
  name: 'navBar'
};
</script>