<template>
  <el-row style="height: 90vh" type="flex" justify="center" align="middle" class="bg-purple-light">
    <el-col :span="6">
      <el-card>
        <el-col>
          <h3 style="text-align: center;margin: 50px 0 50px 0">登录</h3>
        </el-col>
        <!--  捏猫猫的el-form自动刷新机制      -->
        <el-form status-icon ref="loginForm" :model="loginForm" :rules="rules" @submit.prevent.native>
          <el-form-item style="width: 90%; margin-left: 5%;"  >
            <el-input prefix-icon="el-icon-user" v-model="loginForm.username"></el-input>
          </el-form-item>
          <el-form-item style="width: 90%;margin-left: 5%;" prop="password">
            <el-input type="password" v-model="loginForm.password" prefix-icon="el-icon-lock" show-password/>
          </el-form-item>
          <el-button type="primary" style="width: 90%;margin-left: 5%;" native-type="submit" @click="userLogin">登录
          </el-button>
        </el-form>
      </el-card>
    </el-col>
  </el-row>
</template>

<script>
export default {
  data() {
    var validateUsername = (rule, value, callback) => {
      const regEmail = /^([a-zA-Z0-9_-])+@([a-zA-Z0-9_-])+(\.[a-zA-Z0-9_-])+/
      const regInt = /^[\d|\.]*$/

      if (value === '') {
        callback(new Error('用户名不能为空'));
      } else if (!regEmail.test(value) || !(regInt.test(value) && value.length !== 11)) {
        callback(new Error('请输入电话号码或邮箱'));
      } else {
        callback();
      }
    };
    var validatePassword = (rule, value, callback) => {
      if (value === '') {
        callback(new Error('请输入密码'));
      } else {
        callback();
      }
    };
    return {
      loginForm: {
        username: '',
        password: ''
      },
      rules: {
        username: [
          {required: true, validator: validateUsername, trigger: 'blur'}
        ],
        password: [
          {required: true, validator: validatePassword, trigger: 'blur'}
        ]
      }
    }
  },
  methods: {
    async userLogin() {
      try {
        const response = await this.$auth.loginWith('local', {data: this.loginForm})
        this.$router.push('/')
      } catch (err) {
        console.log(err)
      }
    }
  }
}
</script>
