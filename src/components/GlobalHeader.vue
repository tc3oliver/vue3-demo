<template>
  <nav class="navbar navbar-dark bg-primary justify-content-between mb-4 px-4">
    <a href="#" class="navbar-brand">專欄</a>
    <ul v-if="!user.isLogin" class="list-inline mb-0">
      <li class="list-inline-item">
        <a href="#" class="btn btn-outline-light my-2">登入</a>
      </li>
      <li class="list-inline-item">
        <a href="#" class="btn btn-outline-light my-2">註冊</a>
      </li>
    </ul>
    <ul v-else class="list-inline mb-0">
      <li class="list-inline-item">
        <dropdown :title="`你好 ${user.name}`">
          <dropdown-item
            ><a class="dropdown-item" href="#">新建文章</a></dropdown-item
          >
          <dropdown-item disabled
            ><a class="dropdown-item" href="#">編輯資料</a></dropdown-item
          >
          <dropdown-item
            ><a class="dropdown-item" href="#">退出登入</a></dropdown-item
          >
        </dropdown>
      </li>
    </ul>
  </nav>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
import Dropdown from './Dropdown.vue'
import DropdownItem from './DropdownItem.vue'

export interface UserProps {
  isLogin: boolean
  name?: string
  id?: string
}

export default defineComponent({
  name: 'GlobalHeader',
  components: {
    Dropdown,
    DropdownItem,
  },
  props: {
    user: {
      type: Object as PropType<UserProps>,
      required: true,
    },
  },
  setup() {
    return {}
  },
})
</script>

<style scoped></style>
