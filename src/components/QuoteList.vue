<template>
    <div class="row">
            <div class=" panel panel-default">
                <div class=" col-lg-3 col-sm-6 col-md-4 panel panel-body quote-single" @click="deleteQuote(index)" v-for="(quote, index) in quotes">
                    {{ quote }}
                </div>
            </div>
    </div>
</template>

<script>
    import { eventBus } from "../main";

    export  default {
        data() {
            return {
                quotes : [
                    "New Quote goes here!",
                    "New Quote goes here!",
                    "New Quote goes here!",
                    "New Quote goes here!",
                ],
            }
        },
        methods:{
            deleteQuote(index){
                this.quotes.splice( index, 1);
            },

        },
        created(){
            eventBus.$on('busAddQuote', (quote) => {
                this.quotes.push(quote);
            });

        },
        mounted() {
            eventBus.$emit('quotesCount', this.quotes.length);
        },
        updated() {
            eventBus.$emit('quotesCount', this.quotes.length);
        }


    }
</script>

<style>
    .panel-body {
        font-family: 'Arizonia', cursive;
        font-size: 24px;
        color: #6e6e6e;
    }
    .quote-single {
        cursor: pointer;
    }
    .quote-single:hover{
        background-color: #ffe2e2;
    }
</style>