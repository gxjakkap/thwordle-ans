<template>
  <div class="flex justify-center pt-20">
    <Modal v-show="isModalVisible" @close="closeModal" />
    <div
      class="fixed items-top overflow-hidden text-center"
      v-show="!isModalVisible"
    >
      <div class="flex text-center justify-center">
        <h1 class="text-5xl text-center flex py-5">thwordle-answer</h1>
      </div>
      <p class="flex justify-center text-center text-xl">วันที่: {{ day }}</p>
      <p class="flex justify-center text-center">
        {{ today }}
      </p>
      <h2 class="flex justify-center text-center text-2xl">
        คำตอบประจำวันนี้:
      </h2>
      <h2 class="text-4xl mt-5 flex justify-center text-center">{{ word }}</h2>
    </div>
    <Footer />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import word from '~/plugins/words'
import Modal from '~/components/Modal.vue'
export default Vue.extend({
  name: 'IndexPage',
  components: {
    Modal,
  },
  data() {
    const epochDate = 1642525200000
    const today = new Date()
    const todayEp = today.getTime()
    const dateIndex = Math.floor((todayEp - epochDate) / 86400000)
    return {
      isModalVisible: true,
      day: dateIndex + 1,
      today: today.toString(),
      word: word[dateIndex],
    }
  },
  methods: {
    closeModal() {
      this.isModalVisible = false
    },
  },
})
</script>
