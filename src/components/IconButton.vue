<template>
  <button class="icon-button">

  </button>
</template>

<script>
  export default {
    name: "IconButton",
    props: {
      icon: {
        type: String,
        required: true
      },
      isDisabled: {
        type: Boolean,
        default: false
      }
    }
  }
</script>

<style scoped>

</style>