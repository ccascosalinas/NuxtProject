<template lang='pug'>
  div
    b-sidebar(type='is-light' :fullheight='fullheight' :fullwidth='fullwidth' :overlay='overlay' :right='right' v-model='open')
      .p-1
        img(src='https://www.islabit.com/wp-content/uploads/2021/11/agregar-notas-reunion-Docs.png' alt='Lightweight UI components for Vue.js based on Bulma')
        b-menu
          b-menu-list(label='Menu')
            b-menu-item(icon='information-outline' label='')
            b-menu-item(icon='settings')
              template(#label='props')
                | Administrator
                b-icon.is-pulled-right(:icon="props.expanded ? 'menu-down' : 'menu-up'")
              b-menu-item(icon='account' label='Users')
              b-menu-item(icon='cellphone-link')
                template(#label='')
                  | Devices
                  b-dropdown.is-pulled-right(aria-role='list' position='is-bottom-left')
                    template(#trigger='')
                      b-icon(icon='dots-vertical')
                    b-dropdown-item(aria-role='listitem') Action
                    b-dropdown-item(aria-role='listitem') Another action
                    b-dropdown-item(aria-role='listitem') Something else
              b-menu-item(icon='cash-multiple' label='Payments' disabled='')
            b-menu-item(icon='account' label='My Account')
              b-menu-item(label='Account data')
              b-menu-item(label='Addresses')
          b-menu-list
            b-menu-item(label='Expo' icon='link' tag='router-link' target='_blank' to='/expo')
          b-menu-list(label='Actions')
            b-menu-item(label='Logout')
    b-button.is-danger.m-2(@click='open = true') Show
    article.panel.is-primary
      p.panel-heading
        | Repositories
      p.panel-tabs
        a.is-active All
        a Public
        a Private
        a Sources
        a Forks
      .panel-block
        p.control.has-icons-left
          input.input.is-primary(type='text' placeholder='Search')
          span.icon.is-left
            i.fas.fa-search(aria-hidden='true')
      a.panel-block.is-active(href='https://github.com/pugjs/pug' target='_blank')
        span.panel-icon
          i.fas.fa-book(aria-hidden='true')
        |     Pug
      a.panel-block(href='https://github.com/buefy/buefy' target='_blank')
        span.panel-icon
          i.fas.fa-book(aria-hidden='true')
        |     Buefy
      a.panel-block(href='https://github.com/nuxt' target='_blank')
        span.panel-icon
          i.fas.fa-book(aria-hidden='true')
        |     Nuxt
      a.panel-block(href='https://github.com/vuejs/vue' target='_blank')
        span.panel-icon
          i.fas.fa-book(aria-hidden='true')
        |     Vuejs
</template>

<script>
export default {
  data() {
    return {
      open: false,
      overlay: true,
      fullheight: true,
      fullwidth: false,
      right: false
    };
  }
};
</script>

<style>
.p-1 {
  padding: 1em;
}
</style>