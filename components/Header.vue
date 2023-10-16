<!-- Определяю переменные и логику в блоке <script setup>. Этот блок обеспечивает удобство при работе с композицией в компонентах -->
<script setup lang="ts">
// Это пользовательский хук, определённый в "useSettings.ts"
const settings = useSettings();
</script>

<template>
  <Bounded as="header">
    <Logo />
    {{ settings }}
  </Bounded>
</template>
