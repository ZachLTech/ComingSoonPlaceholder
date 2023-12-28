<script setup>
import { computed } from 'vue'
import { useMouse, useWindowSize } from '@vueuse/core'

const { x, y } = useMouse()
const { width, height } = useWindowSize()

const dx = computed(() => Math.abs(x.value - width.value / 2))
const dy = computed(() => Math.abs(y.value - (height.value*0.05) / 2))
const distance = computed(() =>
  Math.sqrt(dx.value * dx.value + dy.value * dy.value)
)

const size = computed(() => Math.max(50 - distance.value / 3, 10))
const opacity = computed(() => Math.min(Math.max(size.value / 300, 0.7), 0.5))
</script>

<template>
    <div>
        <div class="absolute rounded-full -translate-x-1/2 -translate-y-1/2 pointer-events-none overflow-hidden bg-black" :style="{ opacity, left: `${x}px`, top: `${y}px`, width: `${size}px`, height: `${size}px`}" />
    </div>
</template>