<template>
  <div id='bgc'>
    <el-card class='login-card'>
      <el-form :model="loginForm" :rules="loginRules">

        <el-form-item prop="mobile">
          <el-input v-model="loginForm.mobile" placeholder="请输入你的手机号"></el-input>
        </el-form-item>

         <el-form-item prop="password">
          <el-input v-model="loginForm.password" placeholder="请输入你的密码"></el-input>
        </el-form-item>

        <el-form-item>
          <el-button style="width:100%" type="primary">登录</el-button>
        </el-form-item>

      </el-form>
    </el-card>
    
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      //数据对象
      loginForm:{
        //校验字段
        mobile:'',
        password:''
      },
      //校验规则
      loginRules:{
        mobile:[{required:true,message:'手机号不能为空',trigger:'blur'},
        {pattern:/^1[3-9]\d{9}$/,message:'你的手机号格式不正确',trigger:'blur'}],
        password:[{required:true,message:'密码不能为空',trigger:'blur'},
        {min:6,max:16,trigger:'blur',message:'密码长度为6-16位'}]
      }
    }
  }
}
</script>

<style>
#bgc{
  height: 100vh;
  width: 100%;
  background-color: pink;
  display: flex;
  align-items: center;
  justify-content: center;
}
.login-card{
  height: 230px;
  width: 400px;
  
}
</style>
