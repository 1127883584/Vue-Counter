<template>
  <div class="hello">
    <Input type="text" v-model = "counterNumber" style="width: 20%"/>
    <counterGroup :counterNumber = "counterNumber"></counterGroup>
    <CounterSum></CounterSum>
  </div>
</template>

<script>
  import CounterGroup from './CounterGroup'
  import CounterSum from './CounterSum'
export default {
  name: 'Father',
  components: {
    counterGroup: CounterGroup,
    CounterSum: CounterSum
  },
  data(){
    return {
      count: 0,
      counterNumber: 0
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
