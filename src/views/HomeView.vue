<script setup>

import * as CRUD from '@/view-models/httpRequests.js'
import List from './components/List.vue'
import { ref } from "vue"

const data = ref([])

const test = async () => {
  let res = await CRUD.get("items")
  res = res.slice(0, 10)
  data.value = res
}
test()

</script>

<template>
  <main>
    <List :data="data" :key="data"/>
  </main>
</template>
