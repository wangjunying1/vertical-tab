<template>
    <div class="tab-item">
      <div class="left">
        <div :class="activeIndex === index? 'active':''"  v-for="(item,index) in arr" :key="index" @click="itemClick(item, index)">
            <p>{{item}}</p>
        </div>
      </div>
      <div class="right">
        <div class="a1" v-if="activeIndex === 0">a0</div>
        <div class="a1" v-if="activeIndex === 1">a1</div>
        <div class="a1" v-if="activeIndex === 2">a2</div>
        <div class="a1" v-if="activeIndex === 3">a3</div>
      </div>
        
    </div>
</template>

<script>
export default {
  name: 'TabItem',
  props: {
    arr: Array
  },
  data() {
    return {
      activeIndex:0
    }
  },
  methods: {
    itemClick(item, index) {
      this.activeIndex = index
      this.$emit("itemClick", this.activeIndex)
    }
  }
}
</script>

<style scoped>
.tab-item {
  width: 500px;
  height: 500px;
  display: flex;
  flex-direction: column;
}
.left {
  width: 200px;
  /* background-color: green; */
  border-right: 1px solid black;
}
.right {
  flex: 1;
  text-align: center;
}
.active {
  color:red;
  border-right: 1px solid red;
}
</style>
