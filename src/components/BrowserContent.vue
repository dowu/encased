<template>
  <div :class="['browser-content', 'theme-'+theme]">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    name: "BrowserContent",
    props: {
      theme: {
        type: String,
        required: true
      }
    }
  }
</script>

<style scoped lang="scss">
  .browser-content {
    min-height: 400px;
    max-height: 900px;

    &.theme {
      &-light {
        background-color: #FFF;
      }
      &-dark {
        background-color: #38393A;
      }
    }
  }
</style>
