<template>
    <div class="container">
        <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
        <app-new-quote @quoteToAdd="addQuote"></app-new-quote>
        <app-quote-grid :quotes="quotes" @quoteToDel="delQuote"></app-quote-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Click on a Quote to delete!</div>
            </div>
        </div>
    </div>
</template>

<script>
    import Header from './components/Header.vue';
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';

    export default {
        data: function () {
            return {
                quotes: ['Just a Quote', 'Another Quote'],
                maxQuotes: 10,
            }
        },
        components: {
            'app-header': Header,
            'app-quote-grid': QuoteGrid,
            'app-new-quote': NewQuote,
        },
        methods: {
            addQuote(quote) {
                if (this.quotes.length >= 10) {
                    return alert('Please delete Quote first!');
                }
                this.quotes.push(quote);
            },
            delQuote(i) {
                this.quotes.splice(i, 1);
            }
        }
    }
</script>

<style lang="scss">

</style>
