<template>
  <div class="home-container">
    <div class="content">
      <h1>欢迎回来<span class="highlight">.</span></h1>
      <p class="subtitle">祝您今天愉快！</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeView'
}
</script>

<style scoped>
.home-container {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
  background-size: 400% 400%;
  animation: gradient 15s ease infinite;
  padding: 2rem;
}

.content {
  text-align: center;
  background: rgba(255, 255, 255, 0.9);
  padding: 3rem;
  border-radius: 20px;
  box-shadow: 0 8px 32px rgba(31, 38, 135, 0.2);
  backdrop-filter: blur(8px);
}

h1 {
  font-size: 3rem;
  color: #333;
  margin-bottom: 1rem;
}

.highlight {
  background: linear-gradient(120deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-size: 200% auto;
  animation: shine 2s linear infinite;
}

.subtitle {
  color: #666;
  font-size: 1.5rem;
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

@keyframes shine {
  to {
    background-position: 200% center;
  }
}
</style> 