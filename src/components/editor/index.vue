<template>
  <div
    class="editor"
    dropzone="true"
    @dragover="dragoverHandler"
    @drop="dropHandler"
  ></div>
</template>

<script setup lang="ts">
function dragoverHandler(event: DragEvent) {
  event.preventDefault();
}

function dropHandler(event: DragEvent) {
  event.preventDefault();

  const componentData = event.dataTransfer?.getData("component");
  console.log(componentData);
}
</script>

<style scoped lang="less">
.editor {
  height: 100%;
  margin: 10px;
  border: 1px solid #ccc;
  box-sizing: border-box;
}
</style>
