<template>
  <div class="traffic-lights">
    <div class="circle red"></div>
    <div class="circle yellow"></div>
    <div class="circle green"></div>
  </div>
</template>

<script>
  export default {
    name: "TrafficLights"
  }
</script>

<style scoped lang="scss">
  .traffic-lights {
    display: flex;
    flex-wrap: nowrap;
  }

  .circle {
    width: 12px;
    height: 12px;
    border-radius: 100%;
    margin-left: 8px;

    &.red {
      background-color: #EE6A5F;
      border: .5px solid #CE5347;

    }
    &.yellow {
      background-color: #F5BD4F;
      border: .5px solid #D6A243;
    }
    &.green {
      background-color: #61C454;
      border: .5px solid #58A942;
    }
  }
</style>