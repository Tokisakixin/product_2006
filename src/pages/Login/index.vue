<template>
  <div class="login-page">
    <div class="left"></div>
    <div class="login-container">
      <h1 class="title">千锋管理系统</h1>
      <el-form :model="loginForm" status-icon :rules="rules" ref="loginForm" label-width="100px" class="demo-loginForm">
        <el-form-item label="用户名" prop="username">
          <el-input type="text" v-model="loginForm.username" autocomplete="off"></el-input>
        </el-form-item>
        <el-form-item label="密码" prop="password">
          <el-input type="password" v-model="loginForm.password" autocomplete="off"></el-input>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" @click="submitForm('loginForm')">提交</el-button>
        </el-form-item>
      </el-form>
    </div>
    <video src="../../../videos/bg_video.d2d602a9.mp4" muted="muted" autoplay="autoplay" loop="loop" preload="auto" class="bg_video"></video>
  </div>
</template>


<script>
  export default {
    // jsDoc注释
    /**
     * @param {Object} rule 就是一个表单验证对象
     * @param {String}  value 输入值
     * @param {Fuction} callback  校验通过不传参，校验不通过传参
     */
    data() {
      var validateUsername = (rule, value, callback) => {
        //用户名正则，4到16位（字母，数字，下划线，减号）
        // var uPattern = /^[a-zA-Z0-9_-]{4,16}$/;
        if(!value){
          callback("4到16位(字母，数字，下划线，减号)")
        }else{
          callback()
        }

        // if (value === '') {
        //   callback(new Error('请输入用户名'));
        // } else {
        //   if (this.loginForm.password !== '') {
        //     this.$refs.loginForm.validateField('password');
        //   }
        //   callback();
        // }
      };
      var validatePassword = (rule, value, callback) => {
        if(!value){
          callback("请输入密码")
        }else{
          callback()
        }

        // if (value === '') {
        //   callback(new Error('请输入密码'));
        // } else if (value !== this.loginForm.username) {
        //   callback(new Error('两次输入密码不一致!'));
        // } else {
        //   callback();
        // }
      };
      return {
        loginForm: {
          username: '',
          password: '',
        },
        rules: {
          username: [
            { validator: validateUsername, trigger: 'blur' }
          ],
          password: [
            { validator: validatePassword, trigger: 'blur' }
          ]
        }
      };
    },
    methods: {
      submitForm(formName) {
        // console.log(this.$refs[formName]);
        this.$refs[formName].validate((valid) => {
          if (valid) {//本地校验通过
            alert('submit!');
          } else {  //校验失败
            console.log('error submit!!');
            return false;
          }
        });
      },
      resetForm(formName) {
        this.$refs[formName].resetFields();
      }
    }
  }
</script>

