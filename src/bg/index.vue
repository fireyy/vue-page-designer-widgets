<template>
  <img
    width="100%"
    data-type="braid-bg"
    :data-uuid="val.uuid"
    :src="val.url">
</template>

<script>
export default {
  name: 'braid-bg',
  icon: 'file-text',
  title: '背景图',
  setting: {
    type: 'braid-bg',
    isUpload: true,
    href: '',
    belong: 'page'
  },
  props: [
    'val'       // 图片对象
  ]
}
</script>
