<!--  -->
<template>
  <div>
  {{msg}}
      非常好的东西
      <button @click="jump" >路由跳转</button>
  </div>
</template>

<script lang='ts'>
import { reactive,toRefs,onBeforeMount,onMounted} from 'vue'
import { useRouter} from "vue-router"
 
 
export default {
    name: '',
    setup() {
          console.log('1-开始创建组件-setup')
          const data= reactive({
              msg:'fuckyou 你老母'

          })
          onBeforeMount(() => {
              console.log('2.组件挂载页面之前执行----onBeforeMount')
          })
          onMounted(() => {
              console.log('3.-组件挂载到页面之后执行-------onMounted')
          })
            const router=useRouter();
          let jump=()=>{
               router.push({name:'2',params:{userid:'2'}})
          }
          const refData = toRefs(data);
          return {
              ...refData,jump
          }

      }
  };
</script>
<style lang='scss' scoped>
</style>