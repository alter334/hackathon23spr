<!-- Comment -->
カウントアップただし3,5,15の倍数の時には表示がFizzBuzz仕様になる
<script setup lang="ts">
import { ref } from 'vue'
var time = ref(0)
var timetxt = ref('0')
var timer_is_running = ref(false)

const addtime = () => {
  time.value++
  if (time.value % 15 == 0) {
    timetxt.value = 'FizzBuzz'
  } else if (time.value % 5 == 0) {
    timetxt.value = 'Buzz'
  } else if (time.value % 3 == 0) {
    timetxt.value = 'Fizz'
  } else {
    timetxt.value = String(time.value)
  }
}

var interval = 0

const timer = () => {
  if (!timer_is_running.value) {
    interval = setInterval(addtime, 1000)
    timer_is_running.value = true
  } else {
    clearInterval(interval)
    timer_is_running.value = false
  }
}

const reset = () => {
  time.value = 0
  timetxt.value = '0'
}
</script>

<template>
  <div>
    <label> タイマー<br /> </label>
    <div>{{ timetxt }}</div>
    <div v-if="!timer_is_running"><button @click="timer">スタート</button></div>
    <div v-if="timer_is_running"><button @click="timer">ストップ</button></div>
    <button @click="reset">リセット</button>
  </div>
</template>

<style></style>
