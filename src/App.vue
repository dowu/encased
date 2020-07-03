<template>
  <div id="app">
    <Browser :theme="'dark'"></Browser>
  </div>
</template>

<script>

import Browser from "./Browser";
export default {
  name: 'App',
  components: {Browser},
}
</script>

<style lang="scss"></style>
