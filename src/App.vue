<template>
    <div class="container">
        <app-header :quoteCount="quotes.length" :maxQuote="maxQuotes"></app-header>
        <app-new-quote @addNewQuote="newQuote"></app-new-quote>
            <app-quote-grid :quotes="quotes" @deleteQuote="deleteQuote"></app-quote-grid>
        <div class="row">
            <div class="alert alert-info text-center">Note: Click on the note to delete a notes</div>
        </div>
    </div>

</template>

<script>
    import Header from './components/Header.vue';
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';
    export default {
        data:function () {
            return {
                quotes:[
                    'Quote is something cool'
                ],
                maxQuotes:10
            }
        },
        methods:{
            newQuote(quote){
                this.quotes.push(quote);
            },
            deleteQuote(index){
                this.quotes.splice(index,1);
            }
        }
    ,
        components:{
            appHeader:Header,
            appQuoteGrid:QuoteGrid,
            appNewQuote:NewQuote
        }
    }
</script>

<style>
</style>
