<template>
  <Button
    :disabled="disabled"
    :is-loading="isLoading"
    :to="to"
    class="
      flex
      items-center
      justify-center
      text-gray-500
      px-1
      py-1
      rounded-full
      !bg-transparent
      !hover:bg-gray-200
      !dark:hover:bg-gray-600
      hover:text-gray-700
      dark:text-gray-500 dark:hover:text-gray-700
      shadow-none
      border-none
    "
  >
    <Icon :name="icon" />
  </Button>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import { RouteLocationRaw } from 'vue-router';

import Button from '~/components/atomic/Button.vue';
import Icon, { IconNames } from '~/components/atomic/Icon.vue';

export default defineComponent({
  name: 'IconButton',

  components: { Button, Icon },

  props: {
    icon: {
      type: String as PropType<IconNames>,
      required: true,
    },

    disabled: {
      type: Boolean,
      required: false,
    },

    to: {
      type: [String, Object, null] as PropType<RouteLocationRaw | null>,
      default: null,
    },

    isLoading: {
      type: Boolean,
    },
  },
});
</script>