<template lang="">
  <div class="row">
    <div class="col-lg-10 col-sm-8">
      <div class="inner-addon right-addon">
        <i class="bi bi-search"></i>
        <input
          type="search"
          v-model="name"
          v-on:keyup.native.enter="$emit('search', name)"
          @input="(event) => (text = event.target.value)"
          class="form-control"
          placeholder="Search"
        />
      </div>
    </div>
    <div class="col-lg-2 col-sm-4 pt-sm-0 pt-2">
      <button
        class="btn btn-primary rounded-pill d-inline-flexalign-items-center justify-center w-100 fw-bold"
        type="button"
        @click="$emit('search', name)"
      >
        Continue
      </button>
    </div>
  </div>
</template>
<script setup>
import { ref } from '@vue/reactivity'
const name = ref('')
</script>
<style lang="scss">
.inner-addon {
  position: relative;

  &.right-addon .bi {
    right: 10px;
  }

  &.right-addon input[type='search'] {
    padding-left: 30px;
    padding-right: 30px;
  }

  .bi {
    position: absolute;
    padding: 10px;
    font-size: 23px;

    pointer-events: none;
  }
}
</style>
