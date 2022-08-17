<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import { onMounted } from 'vue'
import { Graph } from '@antv/x6';
const data = {
  // 节点
  nodes: [
    {
      id: 'node1', // String，可选，节点的唯一标识
      x: 40,       // Number，必选，节点位置的 x 值
      y: 40,       // Number，必选，节点位置的 y 值
      width: 80,   // Number，可选，节点大小的 width 值
      height: 40,  // Number，可选，节点大小的 height 值
      label: 'hello', // String，节点标签
    },
    {
      id: 'node2', // String，节点的唯一标识
      x: 160,      // Number，必选，节点位置的 x 值
      y: 180,      // Number，必选，节点位置的 y 值
      width: 80,   // Number，可选，节点大小的 width 值
      height: 40,  // Number，可选，节点大小的 height 值
      label: 'world', // String，节点标签
    },
  ],
  // 边
  edges: [
    {
      source: 'node1', // String，必须，起始节点 id
      target: 'node2', // String，必须，目标节点 id
    },
  ],
};
onMounted(() => {
  const graph = new Graph({
    container: document.getElementById('graph-view'),
    width: '100%',
    height: '100%',
    minimap: {
      enabled: true,
      container: document.getElementById('mini')
    },
    panning: true,
  });
  graph.fromJSON(data)
}
)
</script>

<template>
  <div id="graph-view">
  </div>
  <div id="mini"></div>
</template>

<style scoped>

body,#app {
  width: 100%;
  height: 100%;
}
#graph-view {
  width: 100%;
  height: 100%;
}
#mini{
  position: fixed;
  top:0;
  right: 0;
  z-index: 1000;
  border: 1px solid #ccc;
}
</style>
