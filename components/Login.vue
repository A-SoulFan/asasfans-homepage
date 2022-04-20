<template>
  <div class="login_container">
    <div class="login_box">
      <div class="avatar_box">
        <!-- <img src="../assets/logo.png"> -->
      </div>
      <p>
      <div class="loginPart" style="position: relative;transform: translate(36%,170%);">
        <h2>用户登录</h2>
      </div>
      <el-form
        :model="loginForm"
        ref="loginForm"
        :rules="rules"
        rlabel-width="0px"
        class="login_form"
      >
        <el-form-item prop="name">
          <el-input
            v-model="loginForm.name"
            prefix-icon="el-icon-user"
          ></el-input>
        </el-form-item>
        <el-form-item prop="pwd">
          <el-input
            v-model="loginForm.pwd"
            prefix-icon="el-icon-lock"
          ></el-input>
        </el-form-item>
        <el-form-item class="btns">
          <el-button type="primary" @click="login('loginForm')">登录</el-button>
          <el-button type="info" @click="resetLoginForm('loginForm')"
            >重置</el-button
          >
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>

<script>
export default {
  name: "Login",
  data() {
    return {
      loginForm: {
        name: "",
        pwd: "",
      },
      rules: {
        name: [
          { required: true, message: "请输入用户名", trigger: "blur" },
          { min: 3, max: 5, message: "长度在 3 到 5 个字符", trigger: "blur" },
        ],
        pwd: [{ required: true, message: "请输入密码", trigger: "change" }],
      },
    };
  },
  methods: {
    resetLoginForm(formName) {
      console.log(this);
      this.$refs[
        formName
      ].resetFields(); /*idea 会显示unresolved variable $refs*/
    },
    login(formName) {
      this.$refs[formName].validate((valid) => {
        if (valid) {
          alert("submit!");
          this.$emit("loginSure");
        } else {
          console.log("error submit!!");
          return false;
        }
      });
    },
  },
};
</script>

<style lang="less" scoped>
.login_container {
  background-color: aquamarine; /*背景颜色*/
  height: 100%; /*占整个屏幕*/
}
.login_box {
  width: 450px; /*登录框宽*/
  height: 300px; /*登录框高*/
  background-color: #fff6f9;
  border-radius: 3px; /*登录框圆角*/
  position: absolute; /*登录框绝对位置*/
  left: 50%; /*登录框左侧位置50%*/
  top: 260px; /*登录框上方位置50%*/
  transform: translate(-50%, -50%); /*登录框往左自身50%，往下自身高度50%*/
  .avatar_box {
    height: 130px; /*图标高*/
    width: 130px;
    border: 1px solid #685eb9; /*图标边 1像素 实线*/
    border-radius: 50%; /*图标圆角*/
    padding: 10px; /*图标内边距*/
    box-shadow: 0 0 10px #dd6d77; /*图标阴影*/
    position: absolute;
    left: 50%; /*图标左50%*/
    transform: translate(-50%, -50%);
    background-color: #ebe5ff;
    img {
      width: 100%;
      height: 100%;
      border-radius: 50%;
      background-color: aliceblue;
    }
  }
}
.login_form {
  position: absolute;
  bottom: 0;
  width: 100%;
  padding: 0 20px;
  box-sizing: border-box; /*为元素设定的宽度和高度决定了元素的边框盒。*/
}
.btns {
  display: flex; /*Flex布局，可以简便、完整、响应式地实现各种页面布局*/
  justify-content: flex-end; /*元素在主轴（页面）上由右或者下开始排列*/
}
</style>