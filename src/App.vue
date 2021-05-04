<template>
  <div class="container">
    <div class="card-header">Network Speed Convertere</div>
    <div class="card-body">
      <div class="unit-control">
        <div class="unit">Mbps</div>
        <span class="exchange-icon fa-fw fa-stack">
          <i class="far fa-circle fa-stack-2x"></i>
          <i class="fas fa-exchange-alt fa-stack-1x"></i>
        </span>
        <div class="unit">MB/s</div>
      </div>
      <div class="converter">
        <div class="flex-1">
          <div class="converter-title">Set</div>
          <input type="number" class="input-number" min="0" :value="inputValue" @input="handleInputChange"/>
        </div>
        <span class="angle-icon fa-2x" style={{marginTop:30}}>
          <i class="fas fa-angle-right"></i>
        </span>
        <div class="text-right flex-1">
          <div class="converter-title">Show</div>
          <input type="text" class="input-number text-right" disabled :value="convertedValue"/>
        </div>
      </div>
    </div>
    <div class="card-footer">FAST</div>
  </div>
</template>

<script>

import {ref, computed} from 'vue';

export default {
  name: 'App',
  setup() {
    const inputValue = ref(0);
    const convertedValue = computed(() => inputValue.value / 8);
    const handleInputChange = (e) => {
      const {value} = e.target;
      inputValue.value = value;
    };
    return {
      inputValue,
      handleInputChange,
      convertedValue,
    };
  },
}
</script>

<style>
</style>
