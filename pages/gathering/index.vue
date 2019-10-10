<template>
  <div>
    活动页面
    <div v-for="(item, index) in items" :key="index">
      <router-link :to="'/gathering/item/'+item.id">{{item.name}}</router-link>
    </div>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  asyncData() {
    console.log("服务器渲染技术NUXT")
    return axios.get('http://49.234.62.214:7300/mock/5d89e15741e041168ac31ca5/v1/gathering/gathering')
      .then(res => {
        return { items: res.data.data }
      })
  },
}
</script>