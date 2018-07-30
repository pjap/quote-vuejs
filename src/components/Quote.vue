<template>
  <div class="col-md-4 col-sm-6 col-lg-3">
    <div class="panel panel-default">
      <div class="panel-body quote">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    quotes: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped>
  .panel-body {
    font-family: 'Kirang Haerang', cursive;
    font-size: 25px;
    color: #6e6e6e;
    border: 1px solid #cccc;
    padding: 10px;
  }
  .quote {
    cursor: pointer;
  }
  .quote:hover {
    background-color: #ffe2e2;
  }
</style>
