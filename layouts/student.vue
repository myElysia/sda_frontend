<template>
  <div>
    <el-container>
      <el-header>
        <Header/>
      </el-header>
      <el-container>
        <el-aside width="200px" style="height: 90vh">
          <Aside/>
        </el-aside>
        <el-container>
          <el-main>
            <Nuxt/>
          </el-main>
          <el-footer style="height: 30px;text-align:center">
            Copyright © 2023 - 2024 StudentDormAssign. All Rights Reserved.
          </el-footer>
        </el-container>
      </el-container>
    </el-container>
  </div>
</template>
<script setup lang="ts">
import Aside from "../components/Aside.vue";
</script>
