<template>
  <div id="app">
    <div @click="gogogo">To Customer Home Page</div>
    <div @click="tototo">login</div>
    <modal/>
    <group>
      <cell title="title" value="value"></cell>
    </group>
  </div>
</template>

<script>
import Vue from 'vue'
import modal from '../../components/modal.vue'
import { Group, Cell, AlertPlugin } from 'vux'
Vue.use(AlertPlugin)

export default {
  components: {
    modal,
    Group,
    Cell
  },
  data() {
    return {
      msg: 'Use Vue 2.0 Today!'
    }
  },
  created() {
    this.$vux.alert.show({
      title: 'Vux is Cool',
      content: 'Do you agree?',
      onShow() {
        console.log(`Plugin:Im showing`)
      },
      onHide() {
        console.log('2')
      }
    })
  },
  methods: {
    gogogo() {
      // location.assign('../customer/home.html')
      location.href = '/customer/home.html'
    },
    tototo() {
      location.href = '/user/login.html'
    }
  }
}
</script>

<style lang="less">
@import '~vux/src/styles/reset.less';
.index-card {
  width: 800px;
  margin: 100px auto;
}
</style>
