<template>
  <div :class="['browser', 'size-'+browser.size]" ref="browser">
    {{browser.width}}
    {{browser.height}}
    {{browser.size}}
    <browser-header :theme="theme" :size="browser.size"></browser-header>
    <browser-content :theme="theme">
      <slot></slot>
    </browser-content>
  </div>
</template>

<script>
  import BrowserHeader from "./components/BrowserHeader";
  import BrowserContent from "./components/BrowserContent";
  export default {
    name: "Browser",
    components: {BrowserContent, BrowserHeader},
    props: {
      theme: {
        type: String,
        required: true
      }
    },
    data() {
      return {
        browser: {
          width: 0,
          height: 0,
          size: ''
        }
      }
    },
    mounted() {
      this.getBrowserSizing();
    },
    created() {
      window.addEventListener("resize", this.getBrowserSizing);
    },
    destroyed() {
      window.removeEventListener("resize", this.getBrowserSizing);
    },
    methods: {
      getBrowserSizing() {
        this.browser.width = this.$refs.browser.clientWidth;
        this.browser.height = this.$refs.browser.clientHeight;
        this.browser.size = this.browser.width <= 900 ? 'sm' : this.browser.width > 900 && this.browser.width <= 1200 ? 'md' : 'lg';
      }
    }
  }
</script>

<style scoped lang="scss">
  .browser {
    min-width: 800px;
    max-width: 1280px;
    width: 100%;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 0 1px rgba(0,0,0,.7), 0 20px 30px rgba(0,0,0,.3), 0 10px 50px rgba(0,0,0,.2);
  }
</style>
