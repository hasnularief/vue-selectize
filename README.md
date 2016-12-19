# vue-selectize
selectizejs using vue 2

# Requirement
<pre>window.$ = window.jQuery = require('jquery')
require('selectize')</pre>

# How to use
<pre>
&lt;script&gt;
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
&lt;/script&gt;

&lt;template&gt;
  &lt;selectize :options="options" v-model="myOption" :placeholder="'-- My placeholder --'"&gt;&lt;/selectize&gt;
&lt;/template&gt;
</pre>
