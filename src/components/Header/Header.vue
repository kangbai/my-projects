<template>
  <div class="my_headers">
      <Header fixed title="主页"></Header>
  </div>
</template>

<script>
import { Header } from 'mint-ui'
export default {
  components: {
    Header
  }
}
</script>

<style lang="scss">
.my_headers {
  padding-top: px2rem(100);
}
</style>
