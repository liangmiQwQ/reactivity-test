<template>
  <div>
    {{ processedData }}
    <button @click="processedData!.age = 2">Change Data</button>
  </div>
</template>

<script lang="ts" setup>
const { data } = await useAsyncData('mock', async () => {
  // 这里直接返回伪造数据
  return { name: 'kapa', age: 3 }
})

const processedData = ref();

watch(data, (newValue) => {
  processedData.value = newValue
  // 乐观更新实践
})
</script>

<style>

</style>