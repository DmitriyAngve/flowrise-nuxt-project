<script setup lang="ts">
const settings = useSettings();

const { asImageSrc } = usePrismic(); // Использую этот хук и сразу деструктурирую результат, чтобы получить ф-ию для преобразования данных в URL изображения

useSeoMeta({
  title: settings.value?.data.site_title,
  description: settings.value?.data.meta_description,
  ogImage: asImageSrc(settings.value?.data.og_image),
}); // В этой строке вызывается хук, который предназначен для установки мета-тегов SEO для веб-страницы.
</script>

<template>
  <div>
    <Header />
    <slot />
    <Footer />
    <div
      class="fixed inset-0 bg-gradient-to-tr from-emerald-50 to-cyan-50 z-[-1] opacity-50"
    />
  </div>
</template>
