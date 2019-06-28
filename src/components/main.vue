<template>
  <el-container class="main" :style="{ 'min-height': documentClientHeight + 'px' }">
    <main-header></main-header>
    <el-container>
      <main-sidbar :style="{'min-height': mainClentHeight + 'px'}"></main-sidbar>
      <main-content :style="{'min-height': mainClentHeight + 'px'}"></main-content>
    </el-container>
  </el-container>
</template>

<script>
import MainSidbar from './commom/main-sidbar'
import MainHeader from './commom/main-header'
import MainContent from './commom/main-content'
export default {
  name: 'HelloWorld',
  components: {MainHeader, MainSidbar, MainContent},
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      documentClientHeight: 100
    }
  },
  computed: {
    mainClentHeight () {
      return this.documentClientHeight - 80
    }
  },
  methods: {
    // 重置窗口可视高度
    resetDocumentClientHeight () {
      this.documentClientHeight = document.documentElement['clientHeight']
      window.onresize = () => {
        this.documentClientHeight = document.documentElement['clientHeight']
      }
    }
  },
  mounted () {
    this.resetDocumentClientHeight()
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
.main.el-container {
  display: flex;
  flex-direction: column;
}
.el-aside{
  background-color: rgba(0, 0, 0, 0.5)
}
</style>
