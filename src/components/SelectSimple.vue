<template>
  <div class="select_simple">
    <div v-html="first.name" @click="open = !open" class="item_start" />
    <div v-if="open" class="item_w">
      <div
        v-for="item of list"
        @click="select(item)"
        v-bind:key="item.num"
        class="item"
      >
        {{item.name}}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SelectSimple',
  data() {
    return {
      first: this.list[0],
      open: false
    }
  },
  props: { list: Array },
  computed: {
    items () {
      return this.list
    }
  },
  methods: {
    select(val) {
      this.$emit('input', val)
      this.first = val
      this.open = false
    }
  }
}
</script>
<style lang="stylus" scoped>
*
  box-sizing border-box
.select_simple
  position relative
  .item_start
    padding 5px 10px
    background #eee
    max-width 140px
    border 1px solid #ddd
    position absolute
    top 0
    left 0
    cursor pointer
  .item_w
    padding 0
    margin 0
    display flex
    flex-direction column
    max-width 140px
    width auto
    font-size 15px
    position absolute
    top 0
    left 0
    .item
      padding 5px 10px
      background #eee
      width 100%
      border 1px solid #ddd
</style>