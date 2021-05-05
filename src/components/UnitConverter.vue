<template>
  <div class="converter">
  <div class="flex-1">
    <div class="converter-title">Set</div>
    <input type="number" class="input-number" min="0" 
      :value="modelValue" 
      @input="(event) => $emit('update:modelValue', event.target.value)"/>
  </div>
  <span class="angle-icon fa-2x" style={{marginTop:30}}>
    <i class="fas fa-angle-right"></i>
  </span>
  <div class="text-right flex-1">
    <div class="converter-title">Show</div>
    <input 
      type="text" class="input-number text-right" 
      :value="convertedValue"
      disabled
    />
  </div>
</div>
</template>
<script>
import { computed, toRefs } from 'vue'
export default {
  props: { 
    'modelValue': [Number, String], 
  } ,
  setup(props, { emit }) {
    const {modelValue} = toRefs(props);
    const convertedValue = computed(() => modelValue.value / 8);
    return {
      modelValue,
      convertedValue
    };
  },
}
</script>