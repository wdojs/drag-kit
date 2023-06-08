<template>
  <div class="sidebar">
    <div
      v-for="item in components"
      :key="item.id"
      draggable="true"
      class="sidebar-item"
      @dragstart="dragstartHandler($event, item)"
    >
      {{ item.name }}
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

type Component = { id: number; name: string };
const components = ref<Component[]>([
  { id: 1, name: "组件1" },
  { id: 2, name: "组件2" },
  { id: 3, name: "组件3" },
  { id: 4, name: "组件4" },
  { id: 5, name: "组件5" },
  { id: 6, name: "组件6" },
  { id: 7, name: "组件7" },
  { id: 8, name: "组件8" },
]);

function dragstartHandler(event: DragEvent, data: Component) {
  event.dataTransfer?.setData("component", data.name);
}
</script>

<style scoped lang="less">
.sidebar {
  box-sizing: border-box;
  padding: 20px;
  border: 1px solid #ccc;
  margin: 10px;
  &-item {
    height: 50px;
    line-height: 50px;
    padding: 0 20px;
    margin: 10px 0;
    border: 1px dotted #333;
    text-align: center;
    user-select: none;
    cursor: grab;
  }
}
</style>
