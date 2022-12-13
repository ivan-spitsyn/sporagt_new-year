<script setup>
let isShow = ref(false);
</script>

<template>
<div :class="['modal', {'show': isShow}]">
  <div class="modal__wrapper"></div>
  <div class="modal__content">
    <div class="modal__header"></div>
    <div class="modal__body">

    </div>
    <div class="modal__footer"></div>
  </div>
</div>
</template>

<style lang="scss" scoped>
.modal {
  display: none;
}
</style>