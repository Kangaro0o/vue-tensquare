<template>
  <div>
    活动详情
    <div>{{item.id}}</div>
    <br />
    <div>{{item.name}}</div>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  asyncData({ params }) {
    return axios.get(`http://49.234.62.214:7300/mock/5d89e15741e041168ac31ca5/v1/gathering/gathering/${params.id}`)
      .then(res => {
        return { item: res.data.data }
      })
  },
}
</script>