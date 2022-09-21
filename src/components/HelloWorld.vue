<script setup>
import { ref, onMounted } from 'vue'
import sourceData from '@/data.json'
// console.log('sourceData', sourceData)
const dataSource = ref(sourceData)
console.log('dataSource', dataSource)

</script>

<template>
  <div>
    {{ dataSource }}
  </div>
</template>

<style scoped>

</style>
