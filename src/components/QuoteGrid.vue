<template lang="html">
    <div class="row">
        <app-quote v-for="(quote, i) in quotes" @click.native="delQuote(i)">{{ quote }}</app-quote>
    </div>
</template>

<script>
    import Quote from './Quote.vue';

    export default {
        props: ['quotes'],
        components: {
            'app-quote': Quote
        },
        methods: {
            delQuote(i) {
                this.$emit('quoteToDel', i);
            }
        }
    }
</script>

<style lang="css">
</style>
