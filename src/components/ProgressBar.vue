<template>
    <div class="row">
        <p>Quotes added</p>
        <div class="bar">
            <div class="col-lg-12 text-center bar" style="background-color: #236cee; margin: 0; color: white;" :style="{width: 10 * quotes + '%'}" > {{ quotes }} / 10</div>
        </div>
        <br>
    </div>
</template>

<script>
    import { eventBus } from "../main";
    export default {
        // props: ['quotes'],
        data() {
            return {
                quotes: 1,
            }
        },
        mounted(){
            eventBus.$on('quotesCount', (count) => {
                this.quotes = count;
            });
        },
    }

</script>

<style>
    .bar {
        width: 100%;
        height: 25px;
        border-radius: 6px;
        background-color: #eee;
        margin: auto;
        transition: width 500ms;
    }
</style>