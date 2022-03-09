<template lang='pug'>
div
  section.title
    b-button(label='Add your tasks' type='is-primary' size='is-medium' @click='alert')
  .m-2
    .p-1
      .relative.is-flex.is-align-items-center
        .btn
          b-button.btn1.p-5.m-3(@click='addTask()' type='is-primary') +
        input.insert.p-4(v-model='title' type='text')
    card-component(@update='item.state = true' :state='item.state' @delete='deleteTask(i)' :title='item.title' v-for='(item, i) in task' :key='i')

</template>

<script>
import Card from '~/components/Card'
export default {
 data(){
   return {
    task: [],
    title: ''
  }
   },
   methods: {
     addTask(){
       this.task.push({title: this.title, state: false})
       this.title = ''
     },
     deleteTask(parameter){
       this.task.splice(parameter, 1)
     },
      alert() {
                this.$buefy.dialog.alert('Insert your task in the input, after press the simbol plus and see the magic.')
            }
   },
   components:{
  'card-component': Card
}
   
}
</script>

<style scoped>
.insert{
  border: solid 2px gray;
  border-radius: 35px;
  width: 100%;
}
.btn{
  position: absolute;
  right: 0;
}
.btn1{
  border-radius: 45px;
}
.title{
  text-align: center;

}
</style>