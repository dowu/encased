<template>
  <div :class="['browser-header', 'theme-'+theme, 'size-'+size]">
    <browser-header-left v-if="size !== 'sm'" :theme="theme" :size="size"></browser-header-left>
    <browser-header-center :theme="theme" :size="size"></browser-header-center>
    <browser-header-right v-if="size !== 'sm'" :theme="theme" :size="size"></browser-header-right>
  </div>
</template>

<script>
  import BrowserHeaderLeft from "./BrowserHeaderLeft";
  import BrowserHeaderCenter from "./BrowserHeaderCenter";
  import BrowserHeaderRight from "./BrowserHeaderRight";
  export default {
    name: "BrowserHeader",
    components: {BrowserHeaderRight, BrowserHeaderCenter, BrowserHeaderLeft},
    props: {
      theme: {
        type: String,
        required: true
      },
      size: {
        type: String,
        required: true
      }
    }
  }
</script>

<style scoped lang="scss">
  .browser-header {
    padding: 0 12px;
    height: 53px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-sizing: border-box;

    &.theme {
      &-light {
        background-color: #FFF;
        border-bottom: 1px solid #D9D9D9;
      }
      &-dark {
        background-color: #191C1F;
        border-bottom: 1px solid #191C1F;
      }
    }
  }
</style>
