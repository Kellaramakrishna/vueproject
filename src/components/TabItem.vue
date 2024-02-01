<template>
  <li class="tab-item-container">
    <button
      type="button"
      :class="{ 'tab-btn': true, 'active-tab-btn': isActive }"
      @click="onClickTabItem"
    >
      <!--tab-btn is alwasy applied and active-tab-btn is applied based on isActive (boolean value)-->
      {{ tabDetails.displayText }}
    </button>
  </li>
</template>

<script>
export default {
  name: "TabItem",
  props: {
    tabDetails: Object,
    clickTabItem: Function,
    isActive: Boolean,
  },
  methods: {
    onClickTabItem() {
      this.clickTabItem(this.tabDetails.tabId);
    },
  },
};
</script>

<style scoped>
.tab-item-container {
  padding-right: 4px;
}

@media screen and (min-width: 992px) {
  .tab-item-container {
    padding-right: 24px;
  }
}

.tab-btn {
  font-family: "Roboto";
  color: #9aa5b1;
  font-weight: 500;
  font-size: 16px;
  background-color: transparent;
  outline: none;
  border: none;
  cursor: pointer;
}

@media screen and (min-width: 992px) {
  .tab-btn {
    font-size: 24px;
  }
}

.active-tab-btn {
  border-bottom: 2px solid #0b69ff;
  color: #3e4c59;
}
</style>
