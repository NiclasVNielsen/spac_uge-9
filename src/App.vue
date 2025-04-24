<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div class="container body">
    <header>
        <nav>
          <RouterLink to="/">Home</RouterLink>
          <RouterLink to="/about">About</RouterLink>
        </nav>
    </header>
    
    <div class="container main">
      <RouterView />
    </div>
  </div>
</template>

<style lang="sass" scoped>

header
  position: fixed
  top: 0
  left: 0
  height: 100vh
  width: calc(var(--differentContextGap) * 1.5)
  background: var(--second)
  padding: var(--sameContextGap) 0

.main
  width: 100%
  padding: 0

main
  width: 100%

nav
  display: flex
  flex-direction: column

a
  display: flex
  justify-content: center
  align-items: center
  padding: var(--sameContextGap)
  writing-mode: vertical-lr
  transform: rotate(180deg)
  &:hover
    color: var(--neutral)

.container.body
  padding: 0

</style>
