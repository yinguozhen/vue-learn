<template>
  <el-header>
    <div></div>
    <div class="btn_group">
      <el-button type="primary" @click="showIM">IM</el-button>
    </div>
    <im-dialog v-if="dialogVisible" ref="ImDialog"></im-dialog>
  </el-header>
</template>

<script>
import ImDialog from './ImDialog'
export default {
  components: {ImDialog},
  data () {
    return {
      dialogVisible: false
    }
  },
  methods: {
    showIM () {
      this.dialogVisible = true
      this.$nextTick(() => {
        this.$refs.ImDialog.init()
      })
    },
    IMinit () {
      RongIMLib.RongIMClient.init()
      RongIMLib.RongIMEmoji.init()
    }
  },
  mounted () {
    this.IMinit()
  }
}
</script>

<style>
.el-header{
  background-color: blue;
  display: flex;
  justify-content: space-between;
  align-items: center
}
</style>
