<template>
  <v-btn
    v-for="item in theme.socialLinks"
    :key="item.link"
    icon
    target="_blank"
    :href="item.link"
  >
    <v-icon v-if="typeof item.icon === 'string'" :icon="`mdi-${item.icon}`" />

    <!-- eslint-disable-next-line vue/no-v-text-v-html-on-component -->
    <v-icon v-else class="svg-icon" v-html="item.icon.svg" />
  </v-btn>
</template>

<script lang="ts" setup>
import { useData } from 'vitepress'

const { theme } = useData()
</script>

<style scoped lang="scss">
.svg-icon {
  :deep(svg) {
    fill: rgb(var(--v-theme-on-surface));
  }
}
</style>
