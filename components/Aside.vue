<template>
  <el-row class="tac">
    <el-menu default-active="1" :collapse="isCollapses">
      <el-menu-item index="1">
        <i class="el-icon-menu"></i>
        <span>首页</span>
      </el-menu-item>
      <el-menu-item index="2">
        <i class="el-icon-menu"></i>
        <span>我的宿舍</span>
      </el-menu-item>
      <el-menu-item index="3">
        <i class="el-icon-menu"></i>
        <span>宿舍调换</span>
      </el-menu-item>
      <el-menu-item index="4">
        <i class="el-icon-menu"></i>
        <span>校内论坛</span>
      </el-menu-item>
    </el-menu>
    <el-radio-group v-model="isCollapses" style="bottom: 20px;position: fixed;">
      <el-radio-button :label="false">展开</el-radio-button>
      <el-radio-button :label="true">收起</el-radio-button>
    </el-radio-group>
  </el-row>
</template>

<script>
export default {
  data() {
    return {
      isCollapses: true
    }
  }
}
</script>
