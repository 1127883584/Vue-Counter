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
        props: ['sum'],
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
                this.countSum ++;
                this.change = 1;
                this.calSum();
            },
            sub() {
                if(this.count > 0) {
                    this.count --;
                    this.countSum --;
                    this.change = -1;
                    this.calSum();
                }
            },
            calSum() {
                this.$emit('calSum', this.change);
            }
        },
        beforeDestroy() {
            this.$emit('calSum', -this.count);
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
