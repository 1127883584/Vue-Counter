<template>
    <div class="hello">
        <counter v-for="item in parseInt(counterNumber)" @calSum="calSum" :key="item"></counter>
    </div>
</template>

<script>
    import Counter from './Counter'
    export default {
        name: 'Counter',
        props: ['counterNumber'],
        components: {
          counter: Counter
        },
        data(){
            return {
                counterGroupSum: this.sum,
                counterArray: []
            }
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
