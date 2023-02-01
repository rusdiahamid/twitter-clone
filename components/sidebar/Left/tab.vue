<template>
  <div>
    <nuxt-link to="#" class="flex items-center p-3 rounded-full w-min text-black hover:bg-gray-200 dark:hover:bg-dim-200 dark:text-white" :class="defultTransition">
      <div class="w-6 h-6 text-dark">
        <slot name="icon"></slot>
      </div>
      <div class="ml-4 text-xl hidden xl:block" :class="textClasses">
        <slot name="name"></slot>
      </div>
    </nuxt-link>
  </div>
</template>
<script setup>
const { defultTransition } = useTailwindConfig();

const props = defineProps({
  active: {
    type: Boolean,
    default: false,
  },
});

const textClasses = computed(() => (props.active ? 'font-bold' : 'font-normal'));
</script>
