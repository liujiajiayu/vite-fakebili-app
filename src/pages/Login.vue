<template>
  <div id="app-login">
    <el-row>
      <el-col :span="24" class="banner">
        <img src="../assets/img/banner.png" alt="banner" class="banner_img" />
      </el-col>
    </el-row>
    <el-row>
      <el-col :span="24">
        <div class="title-line">
          <span class="tit">登录</span>
        </div>
      </el-col>
    </el-row>
    <el-row class="main" justify="center">
      <el-col :span="6"> <el-empty description="目前这里不放东西" /></el-col>
      <div class="line"></div>
      <el-col :span="6" class="login_box">
        <el-tabs v-model="activeName" class="demo-tabs">
          <el-tab-pane label="密码登录" name="first">
            <el-form
              ref="ruleFormRef"
              :model="ruleForm"
              status-icon
              :rules="rules"
              class="demo-ruleForm"
              label-width="20px"
            >
              <el-form-item prop="pass">
                <el-input
                  v-model="ruleForm.pass"
                  type="password"
                  autocomplete="off"
                  placeholder="你的手机号/邮箱"
                  size="large"
                />
              </el-form-item>
              <el-form-item prop="checkPass">
                <el-input
                  v-model="ruleForm.checkPass"
                  type="password"
                  autocomplete="off"
                  placeholder="密码"
                  size="large"
                />
              </el-form-item>
              <el-form-item class="form_box_back">
                <el-checkbox
                  name="reading"
                  v-model="ruleForm.remember"
                  label="记住我"
                />
                <div class="btn_box_back">
                  <el-button type="text">无法验证</el-button>
                  <el-button type="text">忘记密码</el-button>
                </div>
              </el-form-item>
              <el-form-item class="form_box_login">
                <el-button type="primary" size="large" class="btn"
                  >登录</el-button
                >
                <el-button size="large" class="btn">注册</el-button>
              </el-form-item>
            </el-form>
          </el-tab-pane>
          <el-tab-pane label="短信登录" name="second">
            <el-form
              ref="ruleFormRef"
              :model="ruleForm"
              status-icon
              :rules="rules"
              class="demo-ruleForm"
              label-width="20px"
            >
              <el-form-item prop="pass">
                <el-input
                  v-model="input3"
                  placeholder="填写常用手机号码"
                  class="input-with-select"
                  size="large"
                >
                  <template #prepend>
                    <el-select
                      v-model="select"
                      placeholder="中国大陆"
                      style="width: 110px"
                      size="large"
                    >
                      <el-option label="美国" value="1" />
                      <el-option label="比亚时" value="2" />
                      <el-option label="澳大利亚" value="3" />
                    </el-select>
                  </template>
                </el-input>
              </el-form-item>
              <el-form-item prop="checkPass">
                <el-input
                  v-model="ruleForm.checkPass"
                  type="password"
                  autocomplete="off"
                  placeholder="密码"
                  size="large"
                />
              </el-form-item>
              <el-form-item class="form_box_back">
                <el-checkbox
                  name="reading"
                  v-model="ruleForm.remember"
                  label="记住我"
                />
                <div class="btn_box_back">
                  <el-button type="text">无法验证</el-button>
                  <el-button type="text">忘记密码</el-button>
                </div>
              </el-form-item>
              <el-form-item class="form_box_login">
                <el-button type="primary" size="large" class="btn"
                  >登录</el-button
                >
                <el-button size="large" class="btn">注册</el-button>
              </el-form-item>
            </el-form></el-tab-pane
          >
        </el-tabs>
      </el-col>
    </el-row>
  </div>
</template>

<script setup>
import { ref, reactive } from "vue";

const activeName = ref("first");

const handleClick = (tab, event) => {
  console.log(tab, event);
};
const ruleForm = reactive({
  pass: "",
  checkPass: "",
  age: "",
});
const select = ref("中国大陆");
</script>

<style lang="less">
#app-login {
  .banner {
    background-color: #00a0d8;
    height: 86px;
    img {
      width: 980px;
    }
  }
  .title-line {
    width: 980px;
    height: 28px;
    margin: 40px auto;
    border-bottom: 1px solid #ddd;
    margin-bottom: 28px;
    text-align: center;
    .tit {
      height: 56px;
      line-height: 56px;
      margin: 20px auto;
      padding: 0 20px;
      font-size: 38px;
      background: #fff;
      text-align: center;
    }
  }
  .main {
    height: 400px;
    .login_box {
      height: 100%;
      .demo-tabs {
        margin: 40px;
        > .el-tabs__content {
          padding: 32px 32px 32px 0px;
          color: #6b778c;
          font-size: 32px;
          font-weight: 600;
        }
      }
      .form_box_back {
        .el-form-item__content {
          justify-content: space-between;
        }
      }
      .form_box_login {
        .el-form-item__content {
          justify-content: space-between;
          .btn {
            width: 45%;
          }
        }
      }
    }
    .line {
      border-right: 1px solid #ddd;
      height: 300px;
      margin-top: 28px;
    }
  }
}
</style>
