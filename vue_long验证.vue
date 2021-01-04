<template>
 <div class="iogin">
  <el-card class="box-card">
      <div>mall后台管理系统</div>
   <el-form :model="ruleForm" status-icon :rules="rules" ref="ruleForm" class="demo-ruleForm">
    <el-form-item  prop="username">
     <el-input type="text" v-model="ruleForm.username" placeholder ='请输入账号' ></el-input>
    </el-form-item>
    
    <el-form-item  prop="password">
     <el-input type="password" placeholder ='请输入密码' v-model="ruleForm.password" ></el-input>
    </el-form-item>
     
    <el-form-item>
     <el-button type="primary" @click="submitForm('ruleForm')">登录</el-button>
    </el-form-item>
   </el-form>
  </el-card>
 </div>
</template>

<script>
 import {login} from '@/api/login.js'
 export default{
  data:function(){
   var validatePass = (rule, value, callback) => {
    if (value === '') {
      callback(new Error('请输入密码'));
    } else {
      if (this.ruleForm.checkPass !== '') {
     this.$refs.ruleForm.validateField('checkPass');
      }
      callback();
    }
   };
   return {
    ruleForm:{
     username:'',
     password:''
    },
    rules:{
      username: [
      { required: true, message: '请输入账号', trigger: 'blur' },
      { min: 3, max: 16, message: '长度在 3 到 5 个字符', trigger: 'blur' }
      ],
      password:[
      {required:true,trigger:'blur',message:'请输入密码'},
      {min:3,max:16,trigger:'blur',message:'密码长度为3-16个字符'}
      ]
    }
   }
  },
   methods: {
   submitForm(formName) {
          this.$refs[formName].validate((valid) => {
            if (valid) {
     //验证成功，调用后台接口
     console.log("验证成功，调用后台接口");
     //调用 vuex中的动作
     this.$store.dispatch('mallLogin',this.ruleForm).then(res=>{
      console.log(res);
      this.$message({
       type:'success',
       message:res,
       duration:1000
      })
      //页面跳转
      this.$router.push('/pms/product');
     });
            } else {
              console.log('error submit!!');
              return false;
            }
          });
        },
        resetForm(formName) {
          this.$refs[formName].resetFields();
        }
  