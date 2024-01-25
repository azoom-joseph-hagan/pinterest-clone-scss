<template>
  <div id="dropdown">
    <Btn
      class="round light icon btn-small"
      @click="showDropdown = !showDropdown"
      ><Icon name="heroicons:chevron-down-16-solid" color="grey" size="28"
    /></Btn>
    <div v-if="showDropdown" class="dropdown">
      <ul>
        <li>
          <p class="group-title">Currently In</p>
        </li>
        <li class="user-box">
          <Avatar />
          <div>
            <p class="name-title">John Smith</p>
            <p class="group-title">Personal</p>
            <p class="group-title">john.smith@test.com</p>
          </div>
        </li>
        <li>
          <p class="group-title">Your accounts</p>
        </li>
        <li>
          <p class="option-title">Add account</p>
        </li>
        <li>
          <p class="option-title">Convert to business</p>
        </li>
        <li>
          <p class="group-title">More options</p>
        </li>
        <li>
          <p class="option-title">Add account</p>
        </li>
        <li>
          <p class="option-title">Add account</p>
        </li>
        <li>
          <p class="option-title">Add account</p>
        </li>
      </ul>
    </div>
  </div>
</template>
<script lang="ts" setup>
const showDropdown = ref(false);
</script>
<style scoped lang="scss">
#dropdown {
  position: relative;
}

button {
  width: 100%;
}

.dropdown {
  display: flex;
  flex-direction: column;
  position: absolute;
  right: 0;
  top: 35px;
  width: 300px;
  border-radius: 1rem;
  outline: none;
  border: none;
  background: #fff;
  padding: 5px;
  box-shadow: rgba(0, 0, 0, 0.1) 0px 4px 12px;
  z-index: 10;

  ul {
    list-style: none;
    padding: 0;
    margin: 0;
  }

  li {
    margin-bottom: 15px;
    padding: 0.5rem;
    border-radius: 0.5rem;
    cursor: pointer;
    &:last-child {
      margin-bottom: 0;
    }

    &:hover {
      background-color: #e8e8e8;
    }
  }
}
.group-title {
  font-size: 0.8rem;
  color: #535353;
}

.name-title {
  font-size: 1.1rem;
  font-weight: d;
}

.option-title {
  font-size: 1rem;
  font-weight: bold;
}
.user-box {
  display: flex;
  gap: 0.5rem;
  align-items: center;
  padding: 0.5rem;
  background-color: #e8e8e8;
  border-radius: 0.5rem;
}
</style>
