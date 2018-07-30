<template>
  <div class="container">
    <appHeaderBar :maxQuotes="maxQuotes" :quoteCount="quotes.length"></appHeaderBar>
    <appNewQuote @addNewQuote="newQuote"></appNewQuote>
    <appQuoteGrid :quotes="quotes" @deleteQuote="deleteQuote"></appQuoteGrid>
    <div class="row" v-if="quotes.length > 2">
      <div class="col-sm-12 text-center">
        <div class="alert alert-danger">
          <strong>Attention!</strong> Just Click The Quotes To Delete It.
        </div>
      </div>
    </div>
    <div class="row" v-else>
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">
          <strong>Attention!</strong> Just Input The Quote Area To Add New Quote.
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue'
import NewQuote from './components/NewQuote.vue'
import HeaderBar from './components/Header.vue'

export default {
  data: function() {
    return {
      quotes: ['Just a quote to see something'],
      maxQuotes: 10
    }
  },
  components: {
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote,
    appHeaderBar: HeaderBar
  },
  methods: {
    newQuote(quote) {
      if (quote == '') {
        alert('Please Fill The Quote! Cant Be Empty')
      }
      else if (this.quotes.length < this.maxQuotes) {
        this.quotes.push(quote)
      } else {
        alert('Maximum Of Reached Quotes Are 10 , Please Delete To Create New Quote!!!')
      }
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1)
    }
  }
}
</script>

<style>
</style>
