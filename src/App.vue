<script setup lang="ts">
import { nextTick, ref } from 'vue'
import Graph from 'graphology'
import Sigma from 'sigma'

const container = ref()
const graph = new Graph()
let sigma: Sigma
nextTick(() => {
  sigma = new Sigma(graph, container.value as HTMLElement)
})

graph.addNode('John', { x: 0, y: 10, size: 5, label: 'John', color: 'blue' })
graph.addNode('Mary', { x: 10, y: 0, size: 3, label: 'Mary', color: 'red' })
graph.addEdge('John', 'Mary')
</script>

<template>
  <div ref="container" class="container" />
</template>

<style>
.container {
  position: fixed;
  width: 100vw;
  height: 100vh;
}
</style>
