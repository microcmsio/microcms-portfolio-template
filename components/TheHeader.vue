<template>
  <header class="header">
    <div class="headerContainer">
      <!-- ロゴ -->
      <component :is="isTopPage ? 'h1' : 'p'" class="logo">
        <nuxt-link to="/">My Portfolio</nuxt-link>
      </component>

      <!-- メニュー -->
      <nav>
        <ul class="menu">
          <li>
            <nuxt-link to="/#about" class="menu__link">about</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/works" class="menu__link">works</nuxt-link>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script>
export default {
  computed: {
    // TOPページかどうか
    isTopPage() {
      if (this.$route.name === 'index') return true
      return false
    },
  },
}
</script>

<style lang="scss" scoped>
.header {
  width: 100%;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
  background-color: $base-color-primary;
}

.headerContainer {
  padding: 0 1.5em;
  display: flex;
  justify-content: space-between;
  align-items: center;

  @include mq() {
    padding: 0 4em;
  }
}

.logo {
  color: $text-color-primary;
  font-family: $font-ubuntu;
  font-size: fz(18);
  font-weight: bold;
  letter-spacing: 0;

  @include mq() {
    font-size: fz(24);
  }
}

.menu {
  list-style: none;
  display: flex;
  margin-right: -0.75em;

  &__link {
    font-family: $font-ubuntu;
    font-weight: bold;
    text-transform: capitalize;
    line-height: 64px;
    display: inline-block;
    padding: 0 0.25em;
    position: relative;

    @include mq() {
      padding: 0 0.75em;
    }

    &::after {
      content: '';
      display: block;
      width: 0;
      height: 2px;
      background-color: $key-color-black;
      transition: all 0.3s ease-in-out;
      position: absolute;
      left: 0;
      bottom: 0;
    }

    &:hover {
      &::after {
        width: 100%;
      }
    }
  }
}
</style>
