<template>
  <div>
    <ContentBase>
      <div class="background">
        <main>
          <div class="left">
            <p style="font-size: 24px; text-align: center; ">注册</p>
            <label style="font-size: 20px;text-align:start; color:gray"> 账号<input type="text" :value="data.account"
                placeholder="请输入帐号" class="input"></label>
            <label style="font-size: 20px;text-align:start;color:gray"> 密码<input type="password" :value="data.passwd"
                placeholder="请输入密码" class="input"></label>
            <div class="loginBtn">
              <button class="btnright input" @click="register">注册</button>
            </div>
          </div>
        </main>
      </div>
    </ContentBase>
  </div>
</template>

<script setup>
import ContentBase from '../components/ContentBase';
import { useRouter } from 'vue-router';
import { reactive } from 'vue'
const router = useRouter();

const data = reactive({
  account: 'admin',
  passwd: '123456'
})
// 这里的账户和密码需要校验


const register = () => {
  // Todo: 注册逻辑
  // 这里写向后端发送数据逻辑请求，进行注册操作
  try {
    // await registerUser({ /* 用户对象 */ });
    alert('注册成功');
    router.push('/login'); // 跳转到登录页面
  } catch (error) {
    console.error('注册失败', error);
  }
}
</script>

<style scoped>
main {
  display: flex;
  background-size: contain;
  background-repeat: no-repeat;
  border-radius: 20px;

}

main>.left {
  flex: 1 50%;
  display: flex;
  flex-direction: column;
  padding: 10%;
  gap: 4%;
  background-color: #fff;
  box-sizing: border-box;
  border-radius: 20px;

}

input {
  padding: 10px;
  border: 2px solid #ccc;
  width: 100%;
  border-radius: 5px;
  outline: none;
  font-size: 20px;
}
.input {
  max-width: 400px; /* 设置最大宽度 */
}

.loginBtn {
  margin-left: 6px;
  text-align: center;
  width: 100%;
  padding: 10px;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 20px;
  margin-top: 20px;
}

.btnleft {
  width: 50%;
  background-color: #4CAF50;
  color: white;
  border: none;
  cursor: pointer;
  font-size: 20px;
  border-right: 2px solid black;
}

.btnright {
  width: 50%;
  background-color: #4CAF50;
  color: white;
  border: none;
  cursor: pointer;
  font-size: 20px;
}

.background {
  background-color: #fff;
}

p {
  height: 25px;
  line-height: 25px;
  margin-top: -24px;
}

input {
  margin: 5px;
}

label::before {
  content: ' ';
  display: inline-block;
}
</style>