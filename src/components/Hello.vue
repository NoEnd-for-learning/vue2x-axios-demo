Skip to content
This repository
Search
Pull requests
Issues
Marketplace
Explore
@xrtShu
Sign out
Watch 5
Unstar 25
Fork 21 heuuLZP/vue-axios
Code  Issues 0  Pull requests 0  Projects 0  Wiki  Insights
Branch: master Find file Copy pathvue-axios/src/components/Hello.vue
465403d  on 18 May
@heuuLZP heuuLZP 封装api
1 contributor
RawBlameHistory
53 lines (47 sloc)  781 Bytes
<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
  import http from '../utils/http'
  import api from '../utils/api'
  export default {
    name: 'hello',
    data () {
      return {
        msg: 'Welcome to You'
      }
    },
    mounted: function () {
      this.fetchData()
    },
    methods: {
      fetchData: async function () {
        let params = {
        }
        const res = await http.get(api.right, params)
        if (res.data.success) {
          console.log(res, res.data.data.author_id)
          alert('请求成功')
        }
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1, h2 {
    font-weight: normal;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    display: inline-block;
    margin: 0 10px;
  }
  a {
    color: #42b983;
  }
</style>
