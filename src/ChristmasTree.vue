<template>
  <div>
    <!-- 
      If the size is > 1, 
      then create another layer on top 
      and reduce 'size' by 1 using named slots
    -->
    <ChristmasTree v-if="size > 1" :size="size - 1"/>

    <div class="flex flex-row justify-center">
      <!-- create a tree section with 'size' circles -->
      <div 
      v-for="i in size" 
      class=
        "relative rounded-full bg-green 
        w-16 h-16 -m-1 
        flex justify-center items-center" 
      />
    </div>
  </div>
</template>

<script setup lang="ts">
withDefaults(
  // properties
  defineProps<{
    size: number
  }>(),
  // defaults
  {
    size: 1,
  }
)
</script>
