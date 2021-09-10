<template>
  <div>
   <nav/>
   <header/>
   <main/>


  </div>
</template>

<script>
import { reactive, toRefs, onBeforeMount, onMounted } from 'vue'
import header from "./header.vue"
import nav from "./nav.vue"
import main from "./main.vue"
export default {
  name: 'zhuyemian ',
  components:{header,nav,main},
  setup() {
    console.log('1-开始创建组件-setup')
    const data = reactive({})
    onBeforeMount(() => {
      console.log('2.组件挂载页面之前执行----onBeforeMount')
    })
    onMounted(() => {
      console.log('3.-组件挂载到页面之后执行-------onMounted')
    })
    return {
      ...toRefs(data),
    }
  },
}

</script>
<style scoped lang='less'>
</style>