
<template>
  <div id="app">
    <v-header :seller="seller"/>
  </div>
</template>

<script>
import VHeader from 'components/v-header'
import {getSeller} from 'api'
export default {
  name: 'app',
  data() {
    return {
      seller: {}
    }
  },
  created() {
    this._getSeller()
  },
  components: {
    VHeader
  },
  methods: {
    _getSeller() {
      getSeller().then((seller) => {
        this.seller = seller
      })
    }
  }
}
</script>

<style lang="stylus" scoped>
</style>
