<template>
  <button class="btn"><slot /></button>
</template>
<style lang="scss" scoped>
.btn {
  height: 50px;
  padding: 0.5rem 1.25rem;
  background-color: black;
  color: white;
  outline: none;
  border: none;
  font-size: 1rem;
  cursor: pointer;

  &:hover {
    opacity: 0.8;
  }
}

.icon {
  padding: 0.5rem 0.75rem;
}

.light {
  background-color: transparent;
  color: black;

  &:hover {
    background-color: rgb(232, 232, 232);
  }
}

.btn-small {
  height: 25px;
  padding: 0.1rem;
}
</style>
