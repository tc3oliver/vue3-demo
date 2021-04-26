<template>
  <div class="container">
    <global-header :user="currentUser"></global-header>
    <column-list :list="list"> </column-list>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import 'bootstrap/dist/css/bootstrap.min.css'
import ColumnList, { ColumnProps } from '@/components/CloumnList.vue'
import GlobalHeader, { UserProps } from '@/components/GlobalHeader.vue'

const currentUser: UserProps = {
  isLogin: true,
  name: 'Nick',
}

const testData: ColumnProps[] = [
  {
    id: 1,
    title: 'test1的專欄',
    description:
      '這是test1專欄，一段專欄簡介一段專欄簡介一段專欄簡介一段專欄簡介一段專欄簡介',
    avatar:
      'http://vue-maker.oss-cn-hangzhou.aliyuncs.com/vue-marker/5ee22dd58b3c4520912b9470.jpg?x-oss-process=image/resize,m_pad,h_100,w_100',
  },
  {
    id: 2,
    title: 'test2的專欄',
    description:
      '這是test2專欄，一段專欄簡介一段專欄簡介一段專欄簡介一段專欄簡介一段專欄簡介',
    avatar:
      'http://vue-maker.oss-cn-hangzhou.aliyuncs.com/vue-marker/5ee22dd58b3c4520912b9470.jpg?x-oss-process=image/resize,m_pad,h_100,w_100',
  },
  {
    id: 3,
    title: 'test3的專欄',
    description:
      '這是test3專欄，一段專欄簡介一段專欄簡介一段專欄簡介一段專欄簡介一段專欄簡介',
    // avatar:
    //   'http://vue-maker.oss-cn-hangzhou.aliyuncs.com/vue-marker/5ee22dd58b3c4520912b9470.jpg?x-oss-process=image/resize,m_pad,h_100,w_100',
  },
  {
    id: 4,
    title: 'test4的專欄',
    description:
      '這是test4專欄，一段專欄簡介一段專欄簡介一段專欄簡介一段專欄簡介一段專欄簡介',
    avatar:
      'http://vue-maker.oss-cn-hangzhou.aliyuncs.com/vue-marker/5ee22dd58b3c4520912b9470.jpg?x-oss-process=image/resize,m_pad,h_100,w_100',
  },
]

export default defineComponent({
  name: 'App',
  components: {
    ColumnList,
    GlobalHeader,
  },
  setup() {
    return {
      list: testData,
      currentUser,
    }
  },
})
</script>

<style scoped></style>
