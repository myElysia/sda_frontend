<template>
  <el-main>
    <h2>欢迎使用新生宿舍分配系统。</h2>
    <el-calendar v-model="dataInfo"></el-calendar>
  </el-main>
</template>

<script>
export default {
  name: 'IndexPage',
  layout: 'student',
  data() {
    return {
      dataInfo: new Date()
    }
  }
}
</script>
