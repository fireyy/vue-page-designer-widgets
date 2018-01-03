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
    <img
      :src="val.url">
  </div>
</template>

<script>
const WIDGET_NAME = 'braid-pic'

export default {
  name: WIDGET_NAME,
  icon: '<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-image"><rect x="3" y="3" width="18" height="18" rx="2" ry="2"></rect><circle cx="8.5" cy="8.5" r="1.5"></circle><polyline points="21 15 16 10 5 21"></polyline></svg>',
  title: '图片',
  panel: null,
  setting: {
    type: WIDGET_NAME,
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
    user-select: none;
    -webkit-user-drag: none;
    pointer-events: none;
  }
</style>
