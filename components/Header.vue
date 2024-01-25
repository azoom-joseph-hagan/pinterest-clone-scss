<template>
  <nav class="header-container" :class="scrolled && 'scrolled'">
    <Btn class="round light icon"
      ><Icon name="logos:pinterest" color="grey" size="28"
    /></Btn>
    <Btn class="round">Home</Btn>
    <Btn class="round light">Create</Btn>
    <SearchBar class="round" />
    <Btn class="round light icon"
      ><Icon name="heroicons:bell-16-solid" color="grey" size="28"
    /></Btn>
    <Btn class="round light icon"
      ><Icon
        name="heroicons:chat-bubble-oval-left-ellipsis-16-solid"
        color="grey"
        size="28"
    /></Btn>
    <Btn class="round light icon">
      <Avatar />
    </Btn>

    <DropdownMenu />
  </nav>
</template>
<script lang="ts" setup>
const scrolled = ref(false);

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});

const handleScroll = () => {
  scrolled.value = window.scrollY > 50;
};
</script>
<style lang="scss" scoped>
.header-container {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 1rem;
  gap: 0.5rem;
  position: sticky;
  top: 0;
  background: white;
  z-index: 100;

  &.scrolled {
    box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
  }
}
</style>
