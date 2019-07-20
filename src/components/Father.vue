<template>
  <div class="hello">
    <Input type="text" v-model = "counterNumber" style="width: 20%" @on-change="changeCounterSum"></Input>
    <counterGroup ref="counterGroup" :counterNumber = "counterNumber" @calSum="calSum" :sum="sum"></counterGroup>
    <CounterSum :sum = "sum"></CounterSum>
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
      counterNumber: 0,
      sum: 0
    }
  },
  methods: {
    add(){
        this.count ++;
    },
    sub() {
      if(this.count > 0) {
        this.count --;
      }
    },
    calSum(counterGroupSum){
      this.sum = counterGroupSum;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
