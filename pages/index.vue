<template>
  <div class="flex justify-center pt-20">
    <Modal v-if="isModalVisible" @close="closeModal" />

    <div class="fixed items-top overflow-hidden text-center" v-else>
      <div class="flex text-center justify-center">
        <h1 class="text-5xl text-center flex py-5 text-red-400">
          Thwordle-answer
        </h1>
      </div>
      <hr class="h-5" />
      <p class="flex justify-center text-center text-xl">วันที่: {{ day }}</p>
      <p class="flex justify-center text-center">
        {{ today }}
      </p>
      <h2 class="flex justify-center text-center mt-5 text-2xl">
        คำตอบประจำวันนี้:
      </h2>
      <h2 class="text-4xl mt-3 flex justify-center text-center">{{ word }}</h2>
    </div>
    <Footer />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Modal from '~/components/Modal.vue'
import wl from '~/static/words.json'

export default Vue.extend({
  name: 'IndexPage',
  components: {
    Modal,
  },
  data() {
    const epochDate = 1642525200000
    const today = new Date()
    const todayEp = today.getTime()
    const day = Math.floor((todayEp - epochDate) / 86400000)
    const word = wl.words
    return {
      isModalVisible: true,
      day: day + 1,
      today: today.toString(),
      word: word[day % word.length],
    }
  },
  methods: {
    closeModal() {
      this.isModalVisible = false
    },
  },
})
</script>
