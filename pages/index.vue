<script setup lang="ts">
import { components } from "~/slices";

const prismic = usePrismic();
const { data: page } = useAsyncData("index", () =>
  prismic.client.getByUID("page", "home", {
    fetchLinks: [
      "testimonial.quote",
      "testimonial.avatar",
      "testimonial.name",
      "testimonial.job_title",
    ],
  })
);

useSeoMeta({
  // Устанавливаю заголовок страницы на основе "page.value?.data.meta_title". Это для управления мета тегами SEO для каждой страницы в приложении.

  title: page.value?.data.meta_title ?? undefined,
  description: page.value?.data.meta_description ?? undefined,
  ogImage: prismic.asImageSrc(page.value?.data.meta_image) ?? undefined,
  // OG - Open Graphю
  // В целом этот код обеспечивает правильное заполнение мет-тегов SEO (заголовка, описания, изображения) на основе данных, предоставленных в объекте "page" и хуке "prismic"
});
</script>

<template>
  <SliceZone
    wrapper="main"
    :slices="page?.data.slices ?? []"
    :components="components"
  />
</template>
