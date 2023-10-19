<script setup lang="ts">
import { Content, isFilled } from "@prismicio/client";

const props = defineProps(
  getSliceComponentProps<Content.TestimonialsSlice>([
    "slice",
    "index",
    "slices",
    "context",
  ])
);

// Создается вычисляемое св-во "testimonials", которое возвращает массив отзывов из эементов массива "props.sliceSimulatorVue.items"
const testimonials = computed(() => {
  return (
    props.slice.items
      .map((item) => item.testimonial)
      // применяю фильтрацию, чтобы оставить только элементы, для которых ф-ия "isFilled.contentRelationship(testimonial)" равна "true"
      .filter((testimonial) =>
        isFilled.contentRelationship(testimonial)
      ) as unknown as Content.TestimonialDocument[]
  );
});
</script>

<template>
  <Bounded
    :data-slice-type="slice.slice_type"
    :data-slice-variation="slice.variation"
  >
    <PrismicText
      :field="slice.primary.heading"
      wrapper="h2"
      class="heading heading--md mb-12 text-center"
    />
    {{ testimonials[0].data }}
  </Bounded>
</template>
