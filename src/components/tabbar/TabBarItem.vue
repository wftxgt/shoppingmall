<template>
  <div class="tab-bar-item" @click="itemClick">
    <!-- <slot name="item-icon"></slot>
    <slot name="item-icon-active"></slot>
    <slot name="item-text"></slot> -->
    <!-- 将插槽写在div里，设置插槽的相关样式写在div里。因为slot会被替换掉，写在slot上的属性也会被替换 -->
    <div v-if="!isActive"><slot name="item-icon"></slot></div>
    <div v-else><slot name="item-icon-active"></slot></div>
    <div :class="{active:isActive}"><slot name="item-text"></slot></div>

    </div>
</template>

<script>
export default {
  name: 'TabBarItem',
  props:{
    path: String
  },
  components: {
  },
  data(){
    return{
      // isActive:true
    }
  },
  computed:{
    isActive(){
      return this.$route.path.indexOf(this.path) !== -1
    }
  },
  methods:{
    itemClick(){
      this.$router.push(this.path)
    }
  }
}
</script>

<style>
  .tab-bar-item{
    flex: 1;
    text-align: center;
    /* justify-content: center; */
    height: 49px;
    font-size: 14px;
  }

  .tab-bar-item img{
    width: 24px;
    height: 24px;
    /* 去掉图片下方默认的3px高度 */
    vertical-align: middle;
    margin-top: 3px;
    margin-bottom: 2px;
  }
  .active{
    color:#ff5777;
  }
</style>
