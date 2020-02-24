<template>
    <div class="row">
        <form>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
                <label>Quote</label>
                <textarea class="form-control" rows="3" v-model="quote"></textarea>
            </div>
             <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
                <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
            </div>
        </form>
    </div>
</template>

<script>

export default {

    data: function()
    {
        return {
            quote: ''
        }
    },
    methods: {
        createNew: function() {

            if(this.quote == '')
            {
                alert('You need to type something to submit a quote!')
            }
            else
            {
                this.$emit('quoteAdded', this.quote);
                this.quote = '';
            }
        }
    }
}
</script>

<style scoped>
    .btn
    {
        display: block;
        margin: 15px auto;
    }
</style>