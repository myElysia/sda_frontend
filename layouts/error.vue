<template>
  <el-container>
    <el-header>
      <Header/>
    </el-header>

    <el-main>
      <div style="text-align: center;margin-top: 10%">
        <el-empty v-if="error.statusCode === 404" description="页面不存在">
          <el-button type="primary">
            <NuxtLink style="text-decoration:none;color: white" to="/">返回首页</NuxtLink>
          </el-button>
        </el-empty>
        <el-empty v-else description="发生错误，请联系管理员处理">
          <el-button type="primary">
            <NuxtLink style="text-decoration:none;color: white" to="/">返回首页</NuxtLink>
          </el-button>
        </el-empty>
      </div>
    </el-main>
  </el-container>
</template>

<script>
export default {
  name: "ErrorPage",
  props: ['error'],
}
</script>
