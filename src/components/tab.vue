<template>
  <div class="tab">
    <tab-item :arr="arr"></tab-item>
  </div>
</template>

<script>
import TabItem from './tab-item.vue'
export default {
  name: 'Tab',
  props: {
    msg: String
  },
  components: {
    TabItem
  },
  data() {
    return {
      activeIndex:"",
      arr: [1,2,3,4]
    }
  },
  methods: {
    itemClick(index) {
      this.activeIndex = index
    }
  }
}
</script>

<style scoped>

</style>
