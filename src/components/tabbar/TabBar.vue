<template>
    <div id="tab-bar">
      <slot></slot>
    </div>
</template>

<script>
export default {
  name: 'TabBar',
  components: {
  }
}
</script>

<style>
  #tab-bar{
    display: flex;
    background-color:#f6f6f6;

    position: fixed;
    left: 0;
    right: 0;
    /* left和right这两个属性要写，保证占据整个屏幕的宽度 */
    bottom: 0;
    box-shadow: 0 -1px 1px rgba(100, 100, 100, 0.1);
  }


</style>
