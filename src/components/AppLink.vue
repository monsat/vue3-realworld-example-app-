<template>
  <router-link
    :aria-label="props.name"
    :to="props"
    v-bind="attrs"
  >
    <slot />
  </router-link>
</template>

<script setup lang="ts">
import type { AppRouteNames } from 'src/router'
import { defineProps, withDefaults, useAttrs } from 'vue'
import type { RouteParams } from 'vue-router'
import { RouterLink } from 'vue-router'

const props = withDefaults(defineProps<{
  name: AppRouteNames
  params?: RouteParams
}>(), {
  params: {},
})

const attrs = useAttrs()

</script>
