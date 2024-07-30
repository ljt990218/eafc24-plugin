<script setup lang="ts">
import { useToggle } from '@vueuse/core'
import 'uno.css'

const [show, toggle] = useToggle(false)

console.log('eafc24 v0.0.1')

document.addEventListener('keydown', (event) => {
  if (event.code === 'Space') {
    // 发送到俱乐部
    const fsu_club_btn = document.getElementsByClassName('fsu-club') as HTMLCollectionOf<HTMLButtonElement>
    // 领取奖励
    const call_to_action = document.getElementsByClassName('call-to-action') as HTMLCollectionOf<HTMLButtonElement>

    console.log('空格键被按下')
    console.log(fsu_club_btn)
    console.log(call_to_action)

    if (fsu_club_btn.length > 0) {
      fsu_club_btn[0].click()
    }
    else if (call_to_action.length > 0) {
      call_to_action[0].click()
      call_to_action[0]?.ontouchstart()
    }
  }
})
</script>

<template>
  <div class="fixed right-0 bottom-0 m-5 z-100 flex items-end font-sans select-none leading-1em">
    <div
      class="bg-white text-gray-800 rounded-lg shadow w-max h-min" p="x-4 y-2" m="y-auto r-2"
      transition="opacity duration-300" :class="show ? 'opacity-100' : 'opacity-0'"
    >
      <h1 class="text-lg">
        Vitesse WebExt
      </h1>
      <SharedSubtitle />
    </div>
    <button
      class="flex w-10 h-10 rounded-full shadow cursor-pointer border-none" bg="teal-600 hover:teal-700"
      @click="toggle()"
    >
      <pixelarticons-power class="block m-auto text-white text-lg" />
    </button>
  </div>
</template>
