<template>
  <div class="row">
    <appQuote v-for="(quote, index) in quotes" :key="quote.id" @click.native="deleteQuote(index)">{{ quote }}</appQuote>
  </div>
</template>

<script>
import Quotes from '../components/Quote.vue'

export default {
  props: {
    quotes: {
      type: String,
      required: true
    }
  },
  components: {
    appQuote: Quotes
  },
  methods: {
    deleteQuote(index) {
      this.$emit('deleteQuote', index)
    }
  }
}
</script>

<style scoped>
  .mt20 {
    margin-top: 20px;
  }
</style>
