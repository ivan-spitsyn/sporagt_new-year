<template>
  <div class="container">
    <slot />
  </div>
</template>
<style lang="scss" scoped>
.container {
  width: 100%;
  max-width: 1440px;
  margin: 0 auto;
}

@media (max-width: 1479px) {
  .container {
    max-width: 1240px;
  }
}

@media (max-width: 1279px) {
  .container {
    max-width: 1032px;
  }
}

@media (max-width: 1079px) {
  .container {
    max-width: 600px;
  }
}

@media (max-width: 639px) {
  .container {
    max-width: 290px;
  }
}
</style>