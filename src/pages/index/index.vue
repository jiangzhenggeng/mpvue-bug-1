<template>
  <div>
    <div @click="clickHandle">点击增加 currentIndex </div>
    <block v-for="(item,index) in list" :key="index">
      <test
        v-if="index==currentIndex"
        :item="item"
      />
    </block>
  </div>
</template>

<script>
import test from './test'

export default {
  data () {
    return {
      currentIndex: 0,
      list: (()=>{
        let temp = []
        for (let i=0;i<100;i++){
          temp.push(i)
        }
        return temp
      })()
    }
  },

  components: {
    test
  },

  methods: {
    clickHandle () {
      this.currentIndex += 1
    }
  },
}
</script>
