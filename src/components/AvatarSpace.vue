<script setup lang="ts">
import { sha256 } from 'js-sha256';

const props = withDefaults(
  defineProps<{
    space: { id: string; avatar?: string };
    size?: string;
    previewFile?: File;
  }>(),
  {
    size: '22',
    previewFile: undefined
  }
);

const avatarHash = computed(() => {
  if (!props.space?.avatar) return '';
  const hash = sha256(props.space.avatar).slice(0, 16);
  return `&cb=${hash}`;
});
</script>

<template>
  <BaseAvatar
    :preview-file="previewFile"
    :size="size"
    :src="`https://cdn.stamp.fyi/space/${space.id}?s=${
      Number(size) * 2
    }${avatarHash}`"
  />
</template>
