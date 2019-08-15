<template>
  <div>
      <card text='bssnzd'/>
      <img :src="img" alt="">
      <button @click="getimg">img</button>
  </div>
</template>

<script>
import { formatTime } from '@/utils/index'
import card from '@/components/card'

export default {
  components: {
    card
  },

  data () {
    return {
      img:''
    }
  },
  methods:{
    getimg(){
      console.log(1)
      this.$apis.test().then((res)=>{
        console.log(res)
        this.img="http://res.bestcake.com"+res.Tag.DataList[0].ImgUrl
      })
    }
  }
}
</script>

<style scoped lang='scss'>
img{
  width: 206.5px;
  height: 275px;
}
</style>
