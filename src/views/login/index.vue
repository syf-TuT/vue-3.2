<template>
  <div class="login-container">
    <el-form ref="formRef" :model="form" class="login-form">
      <div class="title-container">
        <h3 class="title">用户登录</h3>
      </div>
      <el-form-item>
        <!-- <el-icon :size="20" class="svg-container">
          <Edit />
        </el-icon> -->
        <svg-icon icon="user" class="svg-container"></svg-icon>
        <el-input v-model="form.name"></el-input>
      </el-form-item>
      <el-form-item>
        <!-- <el-icon :size="20" class="svg-container">
          <Edit />
        </el-icon> -->
        <svg-icon icon="password" class="svg-container"></svg-icon>
        <el-input v-model="form.password"></el-input>
      </el-form-item>
      <el-button type="primary" class="login-button">登录</el-button>
    </el-form>
  </div>
</template>

<script setup>
import { ref } from 'vue'
// import { Edit } from '@element-plus/icons-vue' // eslint-disable-line no-unused-vars
const form = ref({ // eslint-disable-line no-unused-vars
  name: '',
  passowrd: ''
})
</script>

<style lang="scss" scoped>
$bg: #103567;
$dark_gray: #314854;
$light_gray: #eee;
$cursor: #fff;

:deep(.el-input__wrapper) {
  background-color: transparent;
  border: 0;
  box-shadow: none;
}

.login-container {
  min-height: 100%;
  width: 100%;
  background-color: $bg;
  overflow: hidden;

  .login-form {
    position: relative;
    width: 520px;
    max-width: 100%;
    padding: 160px 35px 0;
    margin: 0 auto;
    overflow: hidden;

    box-shadow: none;

    .el-input_wrapper {

      box-shadow: none;
      width: none;
    }

    ::v-deep .el-form-item {
      border: 1px solid rgba(255, 255, 255, 0.1);
      background: rgba(0, 0, 0, 0.1);
      border-radius: 5px;
      color: #454545;
    }

    ::v-deep .el-input {
      display: inline-block;
      height: 47px;
      width: 85%;

      input {
        background: transparent;
        border: 0px;
        //-webkit-appearance: none;
        border-radius: 0px;
        padding: 12px 5px 12px 15px;
        color: $light_gray;
        height: 47px;
        caret-color: $cursor;
      }
    }

    .login-button {
      width: 100%;
      box-sizing: border-box;
    }
  }

  .tips {
    font-size: 16px;
    line-height: 28px;
    color: #fff;
    margin-bottom: 10px;

    span {
      &:first-of-type {
        margin-right: 16px;
      }
    }
  }

  .svg-container {
    padding: 6px 5px 6px 15px;
    color: $dark_gray;
    vertical-align: middle;
    display: inline-block;
  }

  .title-container {
    position: relative;

    .title {
      font-size: 26px;
      color: $light_gray;
      margin: 0px auto 40px auto;
      text-align: center;
      font-weight: bold;
    }

    ::v-deep .lang-select {
      position: absolute;
      top: 4px;
      right: 0;
      background-color: white;
      font-size: 22px;
      padding: 4px;
      border-radius: 4px;
      cursor: pointer;
    }
  }

  .show-pwd {
    // position: absolute;
    // right: 10px;
    // top: 7px;
    font-size: 16px;
    color: $dark_gray;
    cursor: pointer;
    user-select: none;
  }
}
</style>
