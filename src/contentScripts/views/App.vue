<script setup lang="ts">
import 'uno.css'

console.log('eafc24 v0.0.1')

function clearElements() {
  // basePack ut-pack-graphic-view
  const ele = document.getElementsByClassName('ut-pack-graphic-view')
  console.log(ele)

  for (let index = 0; index < ele.length; index++) {
    ele[index].hidden = true
    // ele[index].innerHTML = ''
    // ele[index].style.display = 'none'
  }

  // ut-store-pack-details-view--content
  const ele2 = document.getElementsByClassName('ut-store-pack-details-view--content')
  console.log(ele2)

  for (let index = 0; index < ele2.length; index++) {
    ele2[index].hidden = true
    // ele2[index].innerHTML = ''
    // ele2[index].style.display = 'none'
  }
}

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
    <button
      class="flex w-10 h-10 rounded-full shadow cursor-pointer border-none" bg="teal-600 hover:teal-700"
      @click="clearElements()"
    >
      <pixelarticons-power class="block m-auto text-white text-lg" />
    </button>
  </div>
</template>
