<template>
  <div>
    <div id="nav_wrap">
      <span v-for="(tab, index) in tabs" :key="index" :class="{curr: isCurr == index}" @click="tabsNav(index)">{{tab.name}}</span>
    </div>
    <div>
      <div v-if="isCurr == 0">
        <mt-swipe class="swipe_ind">
          <mt-swipe-item>1</mt-swipe-item>
          <mt-swipe-item>2</mt-swipe-item>
          <mt-swipe-item>3</mt-swipe-item>
        </mt-swipe>
        <index-list></index-list>
      </div>
      <div v-else>2</div>
    </div>
  </div>
</template>

<script>
import { Swipe, SwipeItem } from 'mint-ui'
import IndexList from '@/components/IndexList/IndexList'
export default {
  components: {
    Swipe,
    SwipeItem,
    IndexList
  },
  data () {
    return {
      show: true,
      tabs: [{name: '项目列表'}, {name: '债权转让'}],
      isCurr: 0
    }
  },
  methods: {
    tabsNav (index) {
      this.isCurr = index
    }
  }
}
</script>

<style lang="scss" scoped>
#nav_wrap {
  width: 100%;
  display: flex;
  span {
    flex: 1;
    padding: px2rem(30) 0;
    text-align: center;
    font-size: px2rem(30);
    cursor: pointer;
    &.curr {
      border-bottom: px2rem(3) solid #26a2ff;
      color: #26a2ff;
    }
  }
}

.swipe_ind{
  height: px2rem(450);
  padding: px2rem(10) 0;
  background-color: #ccc;
}
</style>
