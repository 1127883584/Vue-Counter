<template>
    <div class="hello">
        <Button @click="add" type="primary">+</Button>
        <span>{{count}}</span>
        <Button @click="sub">-</Button>
    </div>
</template>

<script>
    export default {
        name: 'Counter',
        data(){
            return {
                count: 0,
                countSum: this.sum,
                change: 0
            }
        },
        methods: {
            add(){
                this.count ++;
                this.$store.dispatch('changeSum', 1)
            },
            sub() {
                this.count --;
                this.$store.dispatch('changeSum', -1)
            }
        },
        beforeDestroy() {
            this.$store.dispatch('changeSum', -this.count)
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
