<script setup>
import About from './components/About.vue';
import MainComp from './components/MainComp.vue';
import Navbar from './components/Navbar.vue';
import { ref, onMounted } from 'vue';
import { useStore } from 'vuex'

const store = useStore()

// 앱이 실행되면 날씨 데이터 가져오기
onMounted(() => {
  console.log("mounted")
  store.dispatch('getWeather')
})

</script>

<template>
  <Navbar />
  <div v-if="!$store.state.toggle">
    <MainComp />
  </div>
  <div v-else>
    <About />
  </div>
</template>

<style scoped lang="scss"></style>
