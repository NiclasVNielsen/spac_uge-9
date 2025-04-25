<script setup>

import * as CRUD from '@/view-models/httpRequests.js'
import List from './components/List.vue'
import { ref } from "vue"

const data = ref([])

const getData = async () => {
  let res = await CRUD.get("items")
  res = res.slice(0, 20)
  data.value = res
}
getData()

</script>

<template>
  <main>
    <List :data="data" :key="data"/>
  </main>
</template>
