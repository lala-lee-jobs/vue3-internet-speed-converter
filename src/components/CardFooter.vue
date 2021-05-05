<template>
  <div 
    class="card-footer" 
    :style={backgroundColor:criteria.backgroundColor}>
    {{criteria.title}}
  </div>
</template>
<script>
import { computed, toRefs } from 'vue'
export default {
  props: {
    inputValue: Number,
  },
  setup(props) {
    const {inputValue} = toRefs(props);
    const criteria = computed(() => {
      let criteria = {};
      if(!inputValue.value) {
        criteria = {
          title: '---',
          backgroundColor:'#d3d8e2',
        };
      } else if(inputValue.value < 15) {
        criteria = {
          title: 'SLOW',
          backgroundColor:'#ee362d',
        };
      } else if(inputValue.value >= 15 && inputValue < 40) {
        criteria = {
          title: 'GOOD',
          backgroundColor:'#1b82f1',
        };
      } else if(inputValue.value >= 40) {
        criteria = {
          title: 'FAST',
          backgroundColor:'#13d569',
        };
      }
      return criteria;
    });
    return {
      criteria,
    };
  },
}
</script>