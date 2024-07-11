<template>
  <el-row>
    <el-col :span="6">
      <h3 style="color: aquamarine">新生宿舍分配系统</h3>
    </el-col>
    <el-col :span="6">
      <el-dropdown>
        <img :src="url" style="height: 50px; width: 50px">
        <el-dropdown-menu slot="dropdown">
          <el-dropdown-item>
            <nuxt-link style="text-decoration:none;color: black" to="/">个人信息</nuxt-link>
          </el-dropdown-item>
          <el-dropdown-item @click.native="userLogout">退出登录</el-dropdown-item>
        </el-dropdown-menu>
      </el-dropdown>
    </el-col>
  </el-row>
</template>

<script>
export default {
  methods: {
    userLogout() {
      console.log('has click.')
      try {
        this.$auth.logout()
        this.$router.push('/logout')
      } catch (e) {
        console.log(e)
      }
    }
  },
  data() {
    return {
      fit: "fill",
      url: "https://img1.baidu.com/it/u=4011019684,838669859&fm=253&fmt=auto&app=138&f=JPEG?w=300&h=300"
    }
  }
}
</script>

