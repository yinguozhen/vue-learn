<template>
  <el-dialog
    v-x
    title="IM"
    :modal="false"
    :visible.sync="dialogVisible"
    :close-on-click-modal=false
    width="30%">
    <span>32</span>
  </el-dialog>
</template>

<script>

export default {
  name: 'IM',
  data () {
    return {
      dialogVisible: false
    }
  },
  methods: {
    init () {
      this.dialogVisible = true
    }
  }
}
</script>
