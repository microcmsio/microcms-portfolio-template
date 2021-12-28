<template>
  <div class="wrapper">
    <TheHeader class="header" />
    <main class="main">
      <Nuxt />
    </main>
    <TheFooter />
  </div>
</template>

<style lang="scss" scoped>
.wrapper {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.header {
  position: fixed;
  z-index: 100;
}

.main {
  flex: 1;
  overflow-x: hidden;
  padding-top: 4em;
}
</style>
