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

const openIndexes = ref([])

function toggle(index) {
  const i = openIndexes.value.indexOf(index)

  if (i === -1) {
    openIndexes.value.push(index)
  } else {
    openIndexes.value.splice(i, 1)
  }
}

function isOpen(index) {
  return openIndexes.value.includes(index)
}
</script>

<template>
  <div class="mt-6 md:mt-8">
    <div
      v-for="(item, index) in items"
      :key="item.id"
      class="py-6 border-t border-purple-100 first:border-t-0 first:pt-0 last:pb-0"
    >
      <button
        type="button" 
        class="flex justify-between w-full gap-6 text-left cursor-pointer"
        @click="toggle(index)"
      >
        <p class="text-base font-semibold text-purple-950 md:text-lg hover:text-violet-600">
          {{ item.question }}
        </p>
        <component
          :is="isOpen(index) ? IconMinus : IconPlus"
          :class="[
              'w-7.5 h-7.5 shrink-0 transition-colors duration-1000',
              isOpen(index)
                ? 'text-purple-950'
                : 'text-violet-600'
            ]"
        />
      </button>
      <Transition name="accordion">
        <div class="mt-6 overflow-hidden" v-show="isOpen(index)">
          <p class="text-sm leading-normal text-purple-600 md:text-base">
            {{ item.answer }}
          </p>
        </div>
      </Transition>
    </div>
  </div>
</template>

<style>
  .accordion-enter-active,
  .accordion-leave-active {
    transition: max-height 300ms ease, opacity 200ms ease;
  }

  .accordion-enter-from,
  .accordion-leave-to {
    transform: translateY(-8px);
    opacity: 0;
  }

  .accordion-enter-to,
  .accordion-leave-from {
    transform: translateY(0);
    opacity: 1;
  }
</style>
