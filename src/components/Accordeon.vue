<script setup>
  import { ref } from 'vue';
  import IconPlus from '@/components/icons/IconPlus.vue';
  import IconMinus from '@/components/icons/IconMinus.vue';

  defineProps({
    items: {
      type: Array,
      required: true,
    },
  })

  const openIndex = ref(null)
</script>

<template>
  <div class="mt-6 md:mt-8">
    <div
      v-for="(item, index) in items"
      :key="item.id"
      class="border-t border-purple-100 first:border-t-0"
    >
      <button
        type="button" 
        class="flex justify-between w-full gap-6 py-6"
        @click="toggle(index)"
      >
        <p class="text-base font-semibold text-purple-950 md:text-lg">
          {{ item.question }}
        </p>
        <component
          :is="openIndex === index ? IconMinus : IconPlus"
          class="w-7.5 h-7.5 text-violet-600 shrink-0"
        />
      </button>
      <div class="mb-6">
        <p class="text-sm leading-normal text-purple-600 md:text-base">
          {{ item.answer }}
        </p>
      </div>
    </div>
  </div>
  
</template>
