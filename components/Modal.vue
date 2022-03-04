<template>
  <div class="fixed bg-slate-100 flex justify-center items-center">
    <div class="bg-white shadow flex flex-col overflow-x-auto">
      <section class="relative px-20 py-10 w-full">
        <div class="flex text-center justify-center">
          <h1
            class="
              text-5xl text-center
              justify-center
              flex
              py-2
              mb-2
              lg:mb-5
              text-red-500
              sm:py-3
              md:py-5
              lg:py-5
              xl:py-5
              2xl:py-5
            "
          >
            !!SPOILER ALERT!!
          </h1>
        </div>

        <p
          class="
            text-xl text-center
            justify-center
            ml-auto
            mr-auto
            w-full
            sm:w-4/5
            md:w-4/5
            lg:w-3/5
            xl:w-3/5
            2xl:w-3/5
            break-words
          "
        >
          การกดปุ่ม "ฉันยอมรับ" ถือว่าเป็นการยอมรับการถูกสปอยคำตอบของเกม
          thwordle และผู้จัดทำเว็บไซต์ thwordle-ans
          ไม่มีส่วนรับผิดชอบต่อการสปอยใดๆที่อาจจะเกิดขึ้นต่อคุณทั้งสิ้น
        </p>
        <p
          class="
            text-xl text-center
            justify-center
            ml-auto
            mr-auto
            py-5
            w-full
            sm:w-4/5
            md:w-4/5
            lg:w-3/5
            xl:w-3/5
            2xl:w-3/5
          "
        >
          เตือนแล้วนะ! <br />(อินเนอร์เชฟป้อม)
        </p>
        <div class="flex text-center justify-center">
          <button
            type="button"
            class="
              bg-green-600
              text-white
              justify-center
              mr-auto
              ml-auto
              w-1/2
              sm:w-1/3
              md:w-1/4
              lg:w-1/4
              2xl:w-1/4
            "
            @click="close"
          >
            ฉันยอมรับ
          </button>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Modal',
  methods: {
    close() {
      this.$emit('close')
    },
  },
}
</script>