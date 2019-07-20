<template>
    <div class="hello">
        <counter v-for="item in parseInt(counterNumber)" @calSum="calSum" :sum ="counterGroupSum" :key="item"></counter>
    </div>
</template>

<script>
    import Counter from './Counter'
    export default {
        name: 'Counter',
        props: ['counterNumber', 'sum'],
        components: {
          counter: Counter
        },
        data(){
            return {
                counterGroupSum: this.sum,
                counterArray: []
            }
        },
        methods: {
            calSum(change){
                // console.log(sum)
                this.counterGroupSum += change;
                this.$emit('calSum', this.counterGroupSum);
            },
            changeCounterSum() {
                this.counterGroupSum = 0
            }
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
