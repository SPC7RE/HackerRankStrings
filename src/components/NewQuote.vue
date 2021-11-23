<template>
    <div class="row">
        <br>
        <textarea v-model="quote" name="" id="" cols="80" rows="5"/>
        <br>
        <button @click="addQuote" class="btn btn-primary center-block">Add Quote</button>
        <hr>
    </div>
</template>

<script>
    import { eventBus } from "../main";

    export default {
        data() {
            return {
                quote: '',
            }
        },
        methods:{
            addQuote(){
                // eventBus.addQuote(this.quote);
                eventBus.$emit('busAddQuote', this.quote);
                this.quote = '';
            },
        },
    }

</script>

<style>
    textarea {
        border-radius: 7px;
        display: block;
        margin-left: auto;
        margin-right: auto;
    }
</style>