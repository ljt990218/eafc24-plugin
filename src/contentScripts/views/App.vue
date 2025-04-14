<script setup lang="ts">
import 'uno.css'

console.log('HYDY-AD V0.0.1')

function clearElements() {
  // console.log('clearElements')
}

// 需要删除的元素
const elementsToRemove = [
  {
    id: 1,
    className: 'popup-close-btn',
  },
  {
    id: 2,
    idName: 'popup-close-btn',
  },
]

// 如果存在，则删除
elementsToRemove.forEach((item) => {
  if (item.className) {
    const elements = document.getElementsByClassName(item.className)
    Array.from(elements).forEach(el => el.remove())
  }
  if (item.idName) {
    const element = document.getElementById(item.idName)
    if (element) {
      element.remove()
    }
  }
})
</script>

<template>
  <div class="fixed right-0 bottom-0 m-5 z-100 flex items-end font-sans select-none leading-1em">
    <button
      class="flex w-10 h-10 rounded-full shadow cursor-pointer border-none"
      bg="teal-600 hover:teal-700"
      @click="clearElements()"
    >
      <pixelarticons-power class="block m-auto text-white text-lg" />
    </button>
  </div>
</template>
