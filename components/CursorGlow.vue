<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { useMouse, useWindowSize } from '@vueuse/core'

const { x, y } = useMouse()
const { width, height } = useWindowSize()

const orbX = ref(x.value)
const orbY = ref(y.value)
const orbSpeed = 0.1 // Adjust this value for the desired delay effect

const updateOrbPosition = () => {
  orbX.value += (x.value - orbX.value) * orbSpeed
  orbY.value += (y.value - orbY.value) * orbSpeed
}

onMounted(() => {
  const updateLoop = () => {
    updateOrbPosition()
    requestAnimationFrame(updateLoop)
  }; updateLoop()
}); onUnmounted(()=>{});

const dx = computed(() => Math.abs(orbX.value - width.value / 2))
const dy = computed(() => Math.abs(orbY.value - height.value / 2))
const distance = computed(() => Math.sqrt(dx.value * dx.value + dy.value * dy.value))

const size = computed(() => Math.max(500 - distance.value / 3, 300))
const opacity = computed(() => Math.min(Math.max(size.value / 300, 0.7), 0.8))
</script>

<template>
  <div>
    <div class="absolute bg-green-500/30 rounded-full -translate-x-1/2 -translate-y-1/2 pointer-events-none blur-3xl overflow-hidden" :style="{ opacity, left: `${orbX}px`, top: `${orbY}px`, width: `${size}px`, height: `${size}px`}" />
  </div>
</template>