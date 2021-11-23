<template>
    <div class="container">
        <h1 class="text-center">{{ quoteTitle }}</h1>

        <progress-bar/>

        <new-quote/>

        <quote-list/>

        <div class="row">
            <div class="col-lg-12 text-center alert alert-info">Hint: Click on Quote to deleted it!</div>
        </div>
    </div>
</template>

<script>
    import NewQuote from './components/NewQuote.vue';
    import ProgressBar from './components/ProgressBar.vue'
    import QuoteList from './components/QuoteList.vue'

    export default {
        data: function(){
            return {
                quoteTitle: 'Inspiring Quotes Notebook',
            }
        },
        components: {
            'new-quote' : NewQuote,
            'progress-bar' : ProgressBar,
            'quote-list' : QuoteList,
        }
    }
</script>
