<template>
  <div>
    {{ data }}
    <button @click="data!.age = 2">Change Data</button>
    使用 deep 选项
  </div>
</template>

<script lang="ts" setup>
const { data } = await useAsyncData('mock', async () => {
  // 这里直接返回伪造数据
  return { name: 'kapa', age: 3 }
},{ deep:true })
</script>

<style>

</style>