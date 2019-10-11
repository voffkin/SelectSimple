<template>
  <div id="app">
    <SelectSimple :list=list @input="onClickChild" />
  </div>
</template>

<script>
import SelectSimple from './components/SelectSimple.vue'

export default {
  name: 'app',
  data() {
    return {
      list: [
        { num: 1, name: 'one' },
        { num: 2, name: 'two' },
        { num: 3, name: 'three' }
      ]
    }
  },
  components: {
    SelectSimple
  },
  methods: {
    onClickChild(val) {
      console.log('onClickChild', val.num)
    }
  }
}
</script>
<style lang="stylus">

</style>
