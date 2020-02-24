<template>
    <div class="row">
        <aQuote v-for="(quote, index) in quotes" @click.native="deleteQuote(index)"> {{quote}}</aQuote>
    </div>
</template>


<script>

import Quote from './Quotes.vue';

export default {
    components: {
        aQuote: Quote
    },
    props:['quotes'],
    methods: {
        deleteQuote: function(index) {
            this.$emit('quoteDeleted', index);
        }
    }
}
</script>

<style scoped>

</style>