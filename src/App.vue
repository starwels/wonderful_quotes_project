<template>
    <div class="container">
        <app-header :quote_count="quotes.length" :max_quotes="max_quotes"></app-header>
        <app-new-quote @quote_added="new_quote"></app-new-quote>
        <app-quote-grid :quotes="quotes" @quote_deleted="delete_quote"></app-quote-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">
                    Info: Click on a Quote to delete it.
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './QuoteGrid.vue'
    import NewQuote from './NewQuote.vue'
    import Header from './Header.vue'
    export default {
        data: function() {
            return {
                quotes: ['Just a quote to see something.'],
                max_quotes: 10
            }
        },
        methods: {
            new_quote(quote) {
                if(this.quotes.length >= this.max_quotes) {
                    return alert('Please delete Quotes first!');
                }
                this.quotes.push(quote);
            },
            delete_quote(index) {
                this.quotes.splice(index, 1);
            }
        },
        components: {
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote,
            appHeader: Header
        }
    }
</script>

<style>
</style>
