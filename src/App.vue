<template lang="">
  <div class="container pt-4">
    <div class="row">
      <div class="col"><SearchInput @search="fetchDomain" /></div>
    </div>

    <div class="row">
      <div v-if="!domainInfo && isLoading == false">
        <div class="col text-center mt-4">
          <h2>Please enter a domain name</h2>
        </div>
      </div>
      <div v-else-if="domainInfo && isLoading == false"><MainCard :domainInfo="domainInfo" /></div>
      <div class="col" v-else>
        <div class="col text-center mt-4">
          <h2>Loading...</h2>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import SearchInput from '@/components/SearchInput.vue'
import MainCard from '@/components/MainCard.vue'
import { ref } from 'vue'
const domainInfo = ref(null)
const isLoading = ref(false)
function fetchDomain(name) {
  if (name && /^[a-zA-Z0-9][a-zA-Z0-9-]{0,61}[a-zA-Z0-9](?:\.[a-zA-Z]{2,})+$/.test(name)) {
    isLoading.value = true
    return new Promise((resolve) =>
      setTimeout(() => {
        const [domain, extension] = name.split('.')
        console.log(domain, extension)
        resolve({
          domain,
          extension,
          prices: [{ value: '$99' }, { value: '$199' }, { value: '$299' }]
        })
      }, 2000)
    ).then((domain) => {
      isLoading.value = false
      domainInfo.value = domain
    })
  }
}
</script>

<style lang="scss"></style>
