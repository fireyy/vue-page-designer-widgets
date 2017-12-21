<template>
  <div class="lz-image"
    :class="[playState ? 'anm-' + val.animationName : '']"
    :style="{
      position: val.belong === 'page' ? 'absolute' : 'relative',
      width: val.width / w * 100 + '%',
      height: val.height / h * 100 + '%',
      left: val.belong === 'page' ? val.left / w * 100 + '%' : '0',
      top: val.belong === 'page' ? val.top / h * 100 + '%' : '0',
      zIndex: val.z
    }">
    <!-- TODO: move data-uuid to parent div -->
    <img data-type="braid-pic"
      :data-uuid="val.uuid"
      :src="val.url">
  </div>
</template>

<script>
import braidPicStyle from './style.vue'

export default {
  name: 'braid-pic',
  icon: 'image',
  title: '图片',
  panel: braidPicStyle,
  setting: {
    type: 'braid-pic',
    isUpload: true,
    hasGuide: true,
    isChild: true,
    left: 0,
    z: 0,
    href: '',                         // 超链接
    belong: 'page',                   // 属于哪个容器
    animationName: ''
  },
  props: [
    'val', 				// 图片对象
    'w', 			    // 包含块的宽
    'h',  	     	// 包含块的高
    'playState'   // 动画播放状态
  ]
}
</script>

<style scoped>
  .lz-image img {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
  }
</style>
