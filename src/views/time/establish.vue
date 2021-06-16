<template>
  <div>
    <ul>
      <li v-for="article in articles">
        {{article.title}}
      </li>
    </ul>
    <input type="text" v-model="num">
    <button @click="getPhone(num)">确定</button>
    <el-button type="info">信息按钮</el-button>
    <div>{{phoneList}}</div>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        articles: [],
        num: '',
        phoneList: []
      }
    },
    mounted () {
      this.fuc()
    },
    methods: {
      fuc () {
        this.$http.jsonp('https://api.douban.com/v2/movie/top250?count=10', {}, {
          headers: {},
          emulateJSON: true
        }).then(function (response) {
          // 这里是处理正确的回调
          this.articles = response.data.subjects
          // this.articles = response.data["subjects"] 也可以
        }).catch((e) => {
          console.error('错误', e)
        })
      },
      getPhone (val) {
        console.log(val)
      }
    }
  }
</script>

<style>
</style>
