<script setup>
const props = defineProps({
  href: {
    type: String,
    default: ''
  },
});
</script>

<template>
  <a v-if="props.href" :href="props.href" class="button">
    <span class="button__text"><slot /></span>
  </a>
  <div v-else class="button">
    <span class="button__text"><slot /></span>
  </div>
</template>

<style lang="scss" scoped>
.button {
  display: inline-flex;
  justify-content: center;
  align-items: center;
  height: 44px;
  padding: 0 20px;
  border-radius: 10px;
  background: #BF2920;
  border: 2px solid #BF2920;
  text-decoration: none;
  cursor: pointer;

  transition: 0.25s;

  &__text {
    font-size: 16px;
    font-weight: 500;
    line-height: 1.2;
  }

  &:deep(svg path) {
    fill: #ffffff;
  }

  &:hover {
    background: #ffffff;
    transition: 0.25s;
    &:deep(svg path) {
      fill: #BF2920;
      transition: 0.25s;
    }
  }
  &:hover & {
    &__text {
      color: #BF2920;
      transition: 0.25s;
    }
  }
}
</style>