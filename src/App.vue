<template>
  <div id="app" class="container">
    <app-header v-bind:quoteCount="quotes.length" v-bind:maxQuote="maxquotes"></app-header>
    <app-new-quote v-on:quoteAdd="newquote"></app-new-quote>
    <app-quote-grid v-bind:quotes="quotes" v-on:quoteDelete="deleteQUotes"></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
          <div class="alert alert-info">
            Info : Click On Quotes To Delete It
          </div>
      </div>
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import NewQuote from './components/NewQuote.vue'
import QuoteGrid from './components/QuoteGrid.vue'
export default {
  data () {
    return {
     quotes:['Really Never Done It Before'],
     maxquotes:10
    }
  },
  methods:{
    newquote(quote){
      if(this.quotes.length >= this.maxquotes){
        alert("Quotes has reached maximum allowed number")
        return
      }
      this.quotes.push(quote)
    },
    deleteQUotes(index){
      this.quotes.splice(index,1)
    }
  },
  components:{
    appQuoteGrid:QuoteGrid,
    appNewQuote:NewQuote,
    appHeader:Header
  }
}
</script>

<style>

</style>
