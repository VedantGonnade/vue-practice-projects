<template>
  <div class="relative top-5 flex justify-center">
    <div class="relative w-1/2 rounded-lg bg-white">
      <!-- Close Button -->
      <div class="absolute top-2 right-2">
        <button class="cursor-pointer" @click="$emit('close')">✖</button>
      </div>

      <!-- Content -->
      <div class="flex flex-col items-center p-7">
        <h1 class="mb-4 text-2xl font-semibold text-gray-800">Modal Title</h1>
        <!-- Styled Divider -->
        <div class="my-3 h-px w-full bg-gray-300"></div>
        <p class="text-center text-sm leading-6 text-gray-600">
          Parish so enable innate in formed missed. Hand two was eat busy fail.
          Stand smart grave would in so. Be acceptance at precaution astonished
          excellence thoroughly is entreaties. Who decisively attachment has
          dispatched. Fruit defer in party me built under first. Forbade him but
          savings sending ham general. So play do in near park that pain. But
          why smiling man her imagine married. Chiefly can man her out believe
          manners cottage colonel unknown. Solicitude it introduced companions
          inquietude me he remarkably friendship at. My almost or horses period.
          Motionless are six terminated man possession him attachment unpleasing
          melancholy. Sir smile arose one share. No abroad in easily relied an
          whence lovers temper by. Looked wisdom common he an be giving length
          mr.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PopUpModel",
};
</script>
