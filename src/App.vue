<template>
    <div class="container">
        <appHeader :quoteCount="quotes.length" :maxQuotes="maxQuotes"></appHeader>
        <app-new-quote @quoteAdded="newQuote"></app-new-quote>
        <appQuoteGrid :quotes="quotes" @quoteDeleted="deleteQuote"></appQuoteGrid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: Click on Quote to delete it</div>
            </div>
        </div>
    </div>
</template>

<script>

    import quoteGrid from './components/QuotesGrid.vue';
    import newQuote from './components/NewQuote.vue';
    import Header from './components/Header.vue';

    export default {
        data: function(){
            return {
                maxQuotes: 10,
                quotes: ['Just a test quote']
            }
        },
        components: {
            appQuoteGrid: quoteGrid,
            appNewQuote: newQuote,
            appHeader: Header
        },
        methods: {
            newQuote: function(quote){

                if(this.quotes.length >= this.maxQuotes )
                {
                    alert('You must delete some quotes before adding new ones')
                }
                else
                {
                    this.quotes.push(quote);
                }
            },
            deleteQuote: function(index)
            {
                this.quotes.splice(index,1);
            }
        }
    }
</script>

<style>
</style>
