<template>
  <div
    class="text-3xl xl:text-5xl text-body-color"
    :class="[margins, centered ? 'text-center' : 'flex justify-between']"
  >
    <slot></slot>
    {{ text }}
    <span v-if="counter" class="relative flex items-center justify-center ml-3">
      <UIcon name="i-heroicons-book-open" />
      <div class="absolute top-[25%] left-[27%] text-lg flex gap-3">
        <span>{{ counter.number }}</span>
        <span>{{ counter.total }}</span>
      </div>
    </span>
  </div>
</template>

<script setup>
const slots = useSlots();

const props = defineProps({
  text: {
    type: String,
    required: false,
  },
  margins: {
    type: String,
    required: false,
    default: "mt-5 mb-10",
  },
  counter: {
    type: Object,
    required: false,
  },
  centered: {
    type: Boolean,
    required: false,
    default: true,
  },
});
</script>
