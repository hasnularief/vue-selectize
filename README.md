# vue-selectize
selectizejs using vue 2

# Requirement
window.$ = window.jQuery = require('jquery')
require('selectize')

# How to use
<script>
import selectize from './Selectize.vue'

export default {
  components: {
    selectize
  },
  
  data() {
    return {
      options: [
        {id: 1, name: 'Options 1'},
        {id: 2, name: 'Options 2'}
      ],
      myOption: null
    }
  }
}
</script>

<template>
  <selectize :options="options" v-model="myOption" :placeholder="'-- My placeholder --'"></selectize>
</template>
