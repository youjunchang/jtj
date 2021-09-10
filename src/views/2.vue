<!--  -->
<template>
  <div>

kaishi  ceshi {{b}}

  </div>
</template>

<script lang='ts'>
import { reactive,toRefs,ref,onBeforeMount,onMounted} from 'vue'
import {useRoute} from "vue-router"
export default {
    name: '',
      setup() {
         let g=useRoute().params.userid;
         const b=ref(g);
          console.log('1-开始创建组件-setup')
          const data= reactive({


          })
          onBeforeMount(() => {
              console.log('2.组件挂载页面之前执行----onBeforeMount')
          })
          onMounted(() => {
              console.log('3.-组件挂载到页面之后执行-------onMounted')
          })
          const refData = toRefs(data);
          return {
              ...refData,b
          }

      }
  };
</script>
<style lang='scss' scoped>
</style>
