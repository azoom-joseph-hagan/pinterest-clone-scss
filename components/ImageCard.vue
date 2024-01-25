<template>
  <div
    class="image-card relative w-full overflow-hidden rounded-xl bg-blue-400"
  >
    <img :src="image.imageUrl" />
  </div>
</template>
<script lang="ts" setup>
const props = defineProps<{
  image: {
    id: number;
    imageUrl: string;
    title: string;
    description: string;
  };
}>();
</script>

<style lang="scss" scoped>
.image-card {
  position: relative;
  width: 100%;
  overflow: hidden;
  border-radius: 2rem;

  img {
    height: 100%;
    object-fit: contain;
  }
}
</style>
