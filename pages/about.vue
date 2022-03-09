<template lang='pug'>
section
  h1.title Team values
  .example-component
    b-field(grouped='' group-multiline='')
      .control
        b-switch(v-model='autoPlay') Autoplay
      .control
        b-switch(v-model='pauseHover' :disabled='!autoPlay') Pause on hover
      .control
        b-switch(v-model='pauseInfo' :disabled='!pauseHover') Pause info
      .control
        b-switch(v-model='drag') Drag event
      .control
        b-switch(v-model='repeat' :disabled='!autoPlay') Repeat
    b-field(grouped='' group-multiline='')
      b-field(label='Value')
        b-numberinput(v-model='carousel' min='0' :max='carousels.length - 1' controls-position='compact')
      b-field(label='Interval')
        b-numberinput(v-model='interval' min='0' controls-position='compact' step='1000' :disabled='!autoPlay')
      b-field(label='Animated')
        b-field
          b-radio-button(v-model='animated' native-value='fade')
            | Fade
          b-radio-button(v-model='animated' native-value='slide')
            | Slide
      b-field(label='Pause Type')
        b-select(v-model='pauseType' :disabled='!pauseInfo')
          option(value='is-white') is-white
          option(value='is-dark') is-dark
          option(value='is-primary') is-primary
  b-carousel.m-5(v-model='carousel' :animated='animated' :has-drag='drag' :autoplay='autoPlay' :pause-hover='pauseHover' :pause-info='pauseInfo' :pause-info-type='pauseType' :interval='interval' :repeat='repeat' @change='info($event)')
    b-carousel-item(v-for='(carousel, i) in carousels' :key='i')
      section(:class='`hero is-medium is-${carousel.color} is-bold`')
        .hero-body.has-text-centered
          h1.title {{carousel.title}}
          b-input(:placeholder='carousel.title')
          p
            | A link that 
            a(href='https://rockcontent.com/es/blog/valores-de-una-empresa/' target='_blank') goes to find more values

</template>

<script>
export default {
    data() {
        return {
            carousel: 0,
            animated: 'fade',
            drag: false,
            autoPlay: false,
            pauseHover: false,
            pauseInfo: false,
            repeat: false,
            pauseType: 'is-primary',
            interval: 3000,
            carousels: [
                { title: 'Love', color: 'dark' },
                { title: 'Slide 2', color: 'primary' },
                { title: 'Responsibility', color: 'info' },
                { title: 'Goodness', color: 'success' },
                { title: 'Perseverance', color: 'warning' },
                { title: 'Understanding', color: 'danger' }
            ]
        }
    },
    methods: {
        info(value) {
            this.carousel = value
            this.$buefy.toast.open({
                message: `This value ${value} !`,
                type: 'is-info'
            })
        }
    }
}
</script>
<style>
.title{
  text-align: center;
  font-size: 30px;
}
</style>