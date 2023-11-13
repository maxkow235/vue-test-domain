<template lang="">
  <span class="badge rounded-pill d-inline-flex align-items-center">
    <i class="bi-check-circle"></i> <slot></slot>
  </span>
</template>

<style lang="scss">
.badge {
  font-size: 15px;
  text-transform: uppercase;
  background-color: transparent;
  text-wrap: wrap;
  padding: 9px 14px;
  font-weight: normal;
  border: 1px solid white;
  i.bi-check-circle {
    display: inline-block;
    font-size: 22px;
    height: 22px;
    width: 22px;
    margin-right: 12px;
  }
}
</style>
