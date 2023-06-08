<script setup lang="ts">
import Sidebar from "./components/sidebar/index.vue";
import Editor from "./components/editor/index.vue";
</script>

<template>
  <div class="main">
    <Sidebar />
    <Editor />
  </div>
</template>

<style scoped lang="less">
.main {
  display: grid;
  grid-template-columns: 240px auto;
  column-gap: 10px;
}
</style>
