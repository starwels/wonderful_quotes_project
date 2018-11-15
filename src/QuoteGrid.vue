<template>
    <div class="row">
        <app-quote v-for="(quote, index) in quotes" @click.native="delete_quote(index)">{{ quote }}</app-quote>
    </div>
</template>

<script>
    import Quote from './Quote.vue'
    export default {
        props: ['quotes'],
        methods: {
            delete_quote(index) {
                this.$emit('quote_deleted', index)
            }
        },
        components: {
            appQuote: Quote
        }
    }
</script>

<style>
</style>