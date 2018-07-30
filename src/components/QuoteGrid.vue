<template>
  <div class="row">
    <appQuote v-for="(quote, index) in quotes" @click.native="deleteQuote(index)">{{ quote }}</appQuote>
  </div>
</template>

<script>
import Quote from '../components/Quote.vue'

export default {
  props: {
    quotes: {
      type: String,
      required: true
    }
  },
  components: {
    appQuote: Quote
  },
  methods: {
    deleteQuote(index) {
      this.$emit('quoteDeleted', index)
    }
  }
}
</script>

<style>

</style>
