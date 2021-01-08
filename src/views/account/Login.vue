<template>
  <div class="account">
    <div class="form_wrap">
      <a-form name="custom-validation" ref="ruleForm">
        <a-form-item>
          <label>用户名</label>
          <a-input type="text" autocomplete="off" />
        </a-form-item>

        <a-form-item>
          <label>密码</label>
          <a-input type="password" autocomplete="off" />
        </a-form-item>

        <a-form-item>
          <div id="captcha-dom" class="nc-container"></div>
          <!--No-Captcha渲染的位置，其中 class 中必须包含 nc-container-->
        </a-form-item>

        <a-form-item>
          <a-button type="primary" html-type="submit">登录</a-button>
        </a-form-item>
      </a-form>
      <div class="fs_12 text_center">
        <a class="color_white">忘记密码</a> |
        <router-link to="/register">注册</router-link>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, onMounted, reactive, toRefs } from "vue";

export default defineComponent({
  name: "Login",
  setup(props) {
    const formConfig = reactive<any>({
      layout: {
        labelCol: { span: 4 },
        wrapperCol: { span: 14 },
      },
    });

    const data = toRefs(formConfig);
    console.log(data);

    onMounted(() => {});

    return {
      ...data,
    };
  },
});
</script>

<style lang="scss" scoped>
@import "./style.scss";
</style>
