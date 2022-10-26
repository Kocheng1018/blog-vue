<script setup lang="ts">
import { ref } from 'vue'

const props = defineProps({
  // 要複製的項目
  target: {
    type: String,
    default: '',
  },
  // 複製項目的名稱
  targetName: {
    type: String,
    default: '網址',
  },
  // 複製修飾文字
  text: {
    type: String,
    default: '已複製',
  },
})

const copiedInput = ref(null)

const handleCopy = () => {
  copyUrl()
}

const copyUrl = () => {
  const _input = copiedInput.value
  _input.value = props.target || window.location.href
  _input.select()
  _input.setSelectionRange(0, 99999)
  document.execCommand('copy')
  showToast()
}
const showToast = () => {
  alert(`${props.targetName}${props.text}`)
}
</script>

<template>
  <div id="copied" @click.stop="handleCopy">
    <slot></slot>
    <input class="hidden" ref="copiedInput" readonly />
  </div>
</template>



<style lang="scss" scoped>
#copied {
  position: relative;
  .hidden {
    opacity: 0;
    right: 200vw;
    position: absolute;
    pointer-events: none;
  }
}
</style>

