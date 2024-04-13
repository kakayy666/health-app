<template>
  <div class="background">
      <header>
          <span style="font-size: 20px;">甲状腺健康资源整合应用</span>
      </header>
      <main>
        <div class="left">
            <p style="font-size: 24px; text-align: center; ">登录</p>
            <label style="font-size: 20px;text-align:start; color:gray"> 账号<input type="text" :value="data.account"  placeholder="请输入帐号"></label>
            <label style="font-size: 20px;text-align:start;color:gray"> 密码<input type="password" :value="data.passwd"  placeholder="请输入密码"></label>
            <div class="loginBtn">
            <button class="btnleft" @click="loginBtn">登录</button>
            <button class="btnright" @click="registerBtn">注册</button>
            </div>
            </div>

          <div class="right"></div>
      </main>
  </div>
</template>

<script setup>
import { reactive } from 'vue'
import { useRouter } from 'vue-router';
const data = reactive({
  account: 'admin',
  passwd: '123456'
})
// 这里的账户和密码需要校验
const account = 'admin'
const passwd = '123456'
const router = useRouter();


const loginBtn = () => {
      if (data.account === account && data.passwd === passwd) {
        console.log('登录成功');
        router.push('/home');
      } else {
        console.log('登录失败');
      }
};

const  registerBtn = () => {
    router.push('/register');
}
</script>

<style scoped>
header{
  text-align: center;
  width:100vw;
  height:7vh;
  background-color: white;
  position: static;
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
  background-color:white;
  box-shadow:0 5px 10px black;
}
main{  
  width: 800px;
  height: 450px;
  display: flex;
  background-image: url('/public/background.png');
  background-size: contain;
  background-repeat: no-repeat;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  box-shadow:4px 4px 4px  gray;
  border-radius: 20px;

}

main > .left{
  flex:1 50%;
display: flex;
flex-direction: column;
padding:10%;
gap :4%;
background-color:#fff;
box-sizing:border-box;
border-radius: 20px 0 0 20px;

}

main>.right{
  flex:1 50%;
}

input{
  padding: 10px; 
  border: 2px solid #ccc;
  width: 100%;
  border-radius: 5px; 
  outline: none; 
  font-size: 20px;
}
.loginBtn{
  margin-left: 6px;
  text-align:center;
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

.btnleft{
  width: 50%;
  background-color: #4CAF50;
  color: white;
  border: none;
  cursor: pointer;
  font-size: 20px;
  border-right: 2px solid black;
} 
.btnright{
  width: 50%;
  background-color: #4CAF50;
  color: white;
  border: none;
  cursor: pointer;
  font-size: 20px;
}
.background{
  width:100vw;
  height:100vh;
  background-color:lightblue ;
  position:relative;
}
p{
  height:25px;
  line-height: 25px;
  margin-top:-24px;
}
input{
  margin:5px;
}
label::before {
  content:' ';
  display: inline-block;
}
</style>