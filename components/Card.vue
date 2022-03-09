<template lang='pug'>
.card(:class="state ? 'p-10' : 'p-5' ")
  .card-content
    | {{title}}
  .actions
    b-button(@click="$emit('update')" type='is-success' label='Done')
    b-button(@click="$emit('delete')" type='is-danger' icon-right='delete')
</template>

<script>
export default {
  name: 'Card',
  props: {
    title: {type: String, default: ''},
    state: {type: Boolean, default: false}
  }
}
</script>

<style scoped>
.card{
  border: solid 3px rgb(31, 199, 15);
  border-radius: 15px;
  color: black;
  background-color: hsla(184, 84%, 49%, 0.2);
  margin: 5px;
  display: flex;
  justify-content: space-between;
}
.actions{
  justify-content: center;
  margin: 15px;
}
</style>