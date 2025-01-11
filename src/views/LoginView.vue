<template>
  <div class="login-container">
    <div class="login-content">
      <h1 class="title">Welcome<span class="highlight">.</span></h1>
      
      <div class="form-container">
        <div class="input-group">
          <label>邮箱</label>
          <input 
            type="email" 
            placeholder="请输入邮箱"
            v-model="email"
            class="input-field"
          >
        </div>
        
        <div class="input-group">
          <label>密码</label>
          <div class="password-field">
            <input 
              :type="showPassword ? 'text' : 'password'"
              placeholder="请输入密码"
              v-model="password"
              class="input-field"
            >
            <button 
              class="toggle-password"
              @click="showPassword = !showPassword"
            >
              {{ showPassword ? '👁' : '👁‍🗨' }}
            </button>
          </div>
        </div>

        <div class="options">
          <label class="remember">
            <input type="checkbox" v-model="remember">
            <span>记住我</span>
          </label>
          <a href="#" class="forgot">忘记密码？</a>
        </div>

        <button 
          class="sign-in-button"
          @click="handleLogin"
        >
          登录
        </button>

        <p class="register-text">
          还没有账号？ <a href="#" class="register-link">立即注册</a>
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LoginView',
  data() {
    return {
      email: '',
      password: '',
      showPassword: false,
      remember: false
    }
  },
  methods: {
    handleLogin() {
      this.$router.push('/home')
    }
  }
}
</script>

<style scoped>
.login-container {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
  background-size: 400% 400%;
  animation: gradient 15s ease infinite;
  padding: 20px;
}

@keyframes gradient {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

.login-content {
  width: 100%;
  max-width: 420px;
  background: rgba(255, 255, 255, 0.9);
  padding: 40px;
  border-radius: 20px;
  box-shadow: 0 8px 32px rgba(31, 38, 135, 0.2);
  backdrop-filter: blur(8px);
}

.title {
  font-size: 2.5rem;
  color: #333;
  margin-bottom: 2rem;
  font-weight: 700;
}

.highlight {
  background: linear-gradient(120deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-size: 200% auto;
  animation: shine 2s linear infinite;
}

@keyframes shine {
  to {
    background-position: 200% center;
  }
}

.input-group {
  margin-bottom: 1.5rem;
}

.input-group label {
  display: block;
  color: #666;
  margin-bottom: 8px;
  font-size: 0.9rem;
}

.input-field {
  width: 100%;
  padding: 12px 16px;
  border: 2px solid #eee;
  border-radius: 12px;
  font-size: 1rem;
  transition: all 0.3s;
  background: rgba(255, 255, 255, 0.9);
}

.input-field:focus {
  outline: none;
  border-color: #23a6d5;
  box-shadow: 0 0 0 4px rgba(35, 166, 213, 0.1);
}

.password-field {
  position: relative;
}

.toggle-password {
  position: absolute;
  right: 16px;
  top: 50%;
  transform: translateY(-50%);
  background: none;
  border: none;
  cursor: pointer;
  font-size: 1.2rem;
}

.options {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1.5rem;
}

.remember {
  display: flex;
  align-items: center;
  gap: 8px;
  color: #666;
  font-size: 0.9rem;
}

.forgot {
  color: #23a6d5;
  text-decoration: none;
  font-size: 0.9rem;
  transition: color 0.3s;
}

.forgot:hover {
  color: #1a7fa6;
}

.sign-in-button {
  width: 100%;
  padding: 14px;
  background: linear-gradient(45deg, #ee7752, #e73c7e);
  color: white;
  border: none;
  border-radius: 12px;
  font-size: 1.1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s;
}

.sign-in-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(231, 60, 126, 0.3);
  background: linear-gradient(45deg, #e73c7e, #23a6d5);
}

.register-text {
  text-align: center;
  margin-top: 1.5rem;
  color: #666;
  font-size: 0.9rem;
}

.register-link {
  color: #23a6d5;
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s;
}

.register-link:hover {
  color: #1a7fa6;
}
</style> 