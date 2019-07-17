<template>
  <van-dialog
    :value="value"
    @input="$emit('input', $event)"
    :showConfirmButton="false"
    closeOnClickOverlay
  >
    <van-cell-group v-if="!isReportShow">
      <van-cell  icon="location-o" title="不感兴趣" @click="handleDislike" />
      <van-cell  icon="location-o" title="反馈垃圾内容" is-link @click="isReportShow = true "/>
      <van-cell  icon="location-o" title="拉黑作者" />
    </van-cell-group>

    <v-cell-group v-else>
      <van-cell icon="arrow-left"/>
      <van-cell icon="location-o" title="拉黑作者" />
      <van-cell icon="location-o" title="拉黑作者" />
      <van-cell icon="location-o" title="拉黑作者" />
      <van-cell icon="location-o" title="拉黑作者" />
    </v-cell-group>
  </van-dialog>
</template>

<script>
// import { dislikeArticle } from '@/api/article'
export default {
  name: 'MoreAction',
  data () {
    return {
      isReportShow: false
    }
  },
  props: {
    value: {
      type: Boolean,
      default: false
    },
    currentArticle: {
      type: Object
    }
  },
  methods: {
    handleDislike () {
      console.log(this.currentArticle)
      // dislikeArticle(文章id？)
    }
  }
}
</script>

<style lang="less" scoped>
</style>
