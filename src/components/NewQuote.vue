<template>
  <div class="row">
    <form>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <label>Give Some Little Quote :)</label>
        <textarea rows="5" cols="80" class="form-control" v-model="quote"></textarea>
      </div>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <button @click.prevent="newQuote" class="btn btn-primary">+ Add New Quote</button>
        <button @click.prevent="clearQuote" class="btn btn-warning">x Clear The Area</button>
      </div>
    </form>
  </div>
</template>

<script>

export default {
  data: function() {
    return {
      quote: ''
    }
  },
  methods: {
    newQuote() {
      this.$emit('addNewQuote', this.quote)
      this.quote = ''
    },
    clearQuote() {
      this.quote = ''
    }
  }
}
</script>

<style scoped>
  .mt20 {
    margin-top: 20px;
  }
  textarea {
    font-family: 'Kirang Haerang', cursive;
    font-size: 20px;
  }
</style>
