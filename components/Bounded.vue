<script setup lang="ts">
defineProps<{ as?: string }>();
</script>

<!--   <Component :is="as || 'section'"></Component> - это пример использования динамического компонента. В этом примере устанавливается компонент, который должен быть отображен, с использованием атрибута ":is" с помощью которого можно определить, какой компонент будет использоваться. ":is" - это директива связывания данных, которая используется для определения того, какой компонент будет отображен -->
<template>
  <Component :is="as || 'section'" class="px-4 py-10 md:py-14 md:px-6 lg:py-16">
    <div class="max-w-6xl w-full mx-auto">
      <slot />
    </div>
  </Component>
</template>
