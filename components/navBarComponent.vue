<template lang='pug'>
div
  b-navbar
    template(#brand='')
      b-navbar-item
        img(src='https://www.islabit.com/wp-content/uploads/2021/11/agregar-notas-reunion-Docs.png')
    template(#start)
      b-navbar-item(href='/') Home page
      b-navbar-item(href='/inspire') Inspire  
      b-navbar-item(href='/about')  About
      b-navbar-item(href='/parent')  Parent
    template(#end='')
      b-navbar-item(tag='div')
        .buttons
          a.button.is-primary
            strong Sign up
          a.button.is-light  Log in 
</template>

<script>
export default {
  name: 'NavbarComponent'
};
</script>