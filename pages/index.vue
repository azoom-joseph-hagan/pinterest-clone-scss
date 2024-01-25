<template>
  <div>
    <Header />
    <main class="image-container">
      <ClientOnly>
        <ImageCard v-for="image in images" :image="image" :key="image.id">
        </ImageCard>
      </ClientOnly>
    </main>
  </div>
</template>
<script lang="ts" setup>
const getRandomSize = (min: number, max: number) => {
  let height = Math.floor(Math.random() * (max - min + 1) + min);
  let width = Math.floor(Math.random() * (max - min + 1) + min);

  height = Math.round(height / 10) * 10;
  width = Math.round(width / 10) * 10;

  return `${height}x${width}`;
};
let images = Array.from({ length: 20 }, (_, index) => ({
  id: index + 1,
  imageUrl: `https://source.unsplash.com/random/${getRandomSize(300, 600)}`,
  title: `Title ${index + 1}`,
  description: `Description for image ${index + 1}`,
}));
</script>
<style lang="scss" scoped>
.image-container {
  display: grid;
  gap: 1rem;
  padding: 1rem;
  grid-template-columns: repeat(2, 1fr);
  margin: 0 auto;
  max-width: 80rem;

  @media (min-width: 640px) {
    grid-template-columns: repeat(3, 1fr);
  }

  @media (min-width: 1280px) {
    grid-template-columns: repeat(4, 1fr);
  }
}
</style>
