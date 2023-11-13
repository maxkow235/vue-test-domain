<template lang="">
  <div class="main-card">
    <div class="p-md-5 px-lg-5 pt-lg-5 pb-lg-0 p-4">
      <div class="row">
        <div class="col-xl-6">
          <Badge class="mb-3">It's a match</Badge>
          <h2 class="fw-lighter">
            {{ domainInfo.domain
            }}<span class="domain fw-bold">{{ '.' + domainInfo.extension }}</span>
          </h2>
          <p>This domain is available, get it now before it's too late!</p>
        </div>
        <div class="col-xl-6">
          <div class="d-flex h-100 align-items-center justify-content-end mt-4 mt-lg-0 flex-wrap">
            <div class="d-inline-flex align-items-center">
              <span class="price-info d-inline-flex align-items-center fs-6"
                >for the first year <i class="bi-info-circle"></i
              ></span>
              <span class="price ms-2 me-3">{{ price }}</span>
            </div>
            <button
              class="btn-cart btn rounded-pill d-inline-flex align-items-center justify-content-center"
              type="button"
            >
              Add to basket <i class="bi-cart-plus"></i>
            </button>
          </div>
        </div>
      </div>
    </div>

    <hr class="border-grey border-1 opacity-20 px-2" />

    <div class="p-md-5 px-lg-5 pb-lg-5 pt-lg-0 p-4">
      <div class="row">
        <div class="col">
          <Features />
        </div>
      </div>
      <div class="row mt-3">
        <div class="col-md-6 col-12 mb-3 mb-md-0">
          <Card>
            <h3 class="card-title fw-bolder">You've picked well...</h3>

            <ul class="card-text mt-3">
              <li>Recieve a <b>20% discount</b> for 3+ years purchased</li>
              <li><b>30%</b> of e-commerce stores use (domain)</li>
              <li>This domain has been searched 1,234 times</li>
            </ul>
          </Card>
        </div>
        <div class="col-md-6 col-12">
          <Card>
            <h4 class="card-title">Registration period:</h4>
            <select
              v-model="price"
              class="form-select mt-3 mb-2"
              aria-label="Default select example"
            >
              <option
                v-for="(domainPrice, index) in props.domainInfo.prices"
                :value="domainPrice.value"
              >
                {{ index + 1 }} Yrs - {{ domainPrice.value }}
              </option>
            </select>
            <p>Renews Jan 2024 for $246/yr <i class="bi-info-circle"></i></p>
          </Card>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
import { defineProps, ref } from 'vue'
import Badge from './Badge.vue'
import Features from './Features.vue'
import Card from './Card.vue'
const props = defineProps(['domainInfo'])
const price = ref(props.domainInfo.prices[0].value)
</script>
<style lang="scss">
.main-card {
  border-radius: 10px;
  background-color: #2d2e34;
  color: #fff;
  margin: 40px 0;

  .price {
    font-size: 30px;
  }
  .price-info {
    font-size: 18px;

    i {
      display: inline-flex;
      font-size: 24px;
      height: 24px;
      width: 24px;
      margin-left: 10px;
    }
  }

  button.btn-cart {
    height: 54px;
    font-size: 20px;
    font-weight: 700;
    color: #2d2e34;
    border-radius: 27px;
    padding: 15px 32px;
    background-color: #fff;
    i {
      display: inline-flex;
      font-size: 24px;
      height: 24px;
      width: 24px;
      margin-left: 10px;
    }

    &:hover {
      color: #fff;
      background-color: transparent;
      border: 1px solid white;
    }
  }

  select.form-select {
    height: 64px;
    padding: 16px;
    font-size: larger;

    .styled-select select {
      -moz-appearance: none;
      -webkit-appearance: none;
      appearance: none;
    }
  }
}
</style>
