<script setup lang="ts">
import { Content } from "@prismicio/client";

// The array passed to `getSliceComponentProps` is purely optional.
// Consider it as a visual hint for you when templating your slice.
defineProps(
  getSliceComponentProps<Content.FeaturesSlice>([
    "slice",
    "index",
    "slices",
    "context",
  ])
);
</script>

<template>
  <Bounded
    :data-slice-type="slice.slice_type"
    :data-slice-variation="slice.variation"
  >
    <PrismicRichText
      :field="slice.primary.heading"
      wrapper="h2"
      class="heading heading--md mb-12 text-center"
    />
    <div class="grid sm:grid-cols-2 lg:grid-cols-4">
      <div v-for="item of slice.items" :key="item.icon ?? ''">
        {{ item.icon }}
        <PrismicText
          :field="item.title"
          wrapper="h3"
          class="heading heading--sm !font-medium pb-3"
        />
        <PrismicRichText :field="item.description" />
      </div>
    </div>
  </Bounded>
</template>
