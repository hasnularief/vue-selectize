<template>
	<select>
   <option v-bind:value="null">{{placeholder}}</option> 
  </select>
</template>

<script>
  export default {
  	props: ['options', 'value','placeholder','valuefield','labelfield','searchfield'],
    mounted: function () {
    	const vm = this
      this.selectize = $(this.$el).selectize({
        valueField: this.valuefield ? this.valuefield : 'id',
        labelField: this.labelfield ? this.labelfield : 'name',
        searchField: this.searchfield ? this.searchfield : 'name',
        options: this.options
      }).on('change', function() {
        vm.$emit('input', this.value)
      })
    },
    watch: {
      value: function (value) {
        // update value	
        var control = this.selectize[0].selectize
        control.setValue(value)
        
      },
      options: function (options) {
        // update options
        var control = this.selectize[0].selectize
        control.clear();
        control.clearOptions();
        control.load(function(callback) {
          callback(options)
          
        });        
      }
    },
    destroyed: function () {
      //$(this.$el).off().select2('destroy')
    }
  }
</script>
<style>
  
</style>
