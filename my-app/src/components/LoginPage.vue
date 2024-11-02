<template>
  <div class="container">
    <div class="left-side">
      <div class="logo">
        <img src="/logo.png" alt="EasyMiles" />
        <span>CAR RENTAL</span>
      </div>
      <div class="content">
        <h1>Sign in to</h1>
        <h2><span class="highlight">EasyMiles</span> Easy Way to Rent</h2>
        <p>
          If you don't have an account, register  <router-link to="/signup">Register here!</router-link>
        </p>
      </div>
      <div class="car">
        <img src="@/assets/car.png">
      </div>
    </div>
    <div class="right-side">
      <form class="form" @submit.prevent="handleSubmit">
        <h3>Sign in</h3>
        <div class="input-group">
          <input type="email" id="email" v-model="email" placeholder="Enter email or user name" required />
        </div>
        <div class="input-group password-group">
          <input :type="showPassword ? 'text' : 'password'" id="password" v-model="password" placeholder="Password" required />
          <span class="eye-icon" @click="togglePassword">
            <i :class="showPassword ? 'fas fa-eye-slash' : 'fas fa-eye'"></i>
          </span>
        </div>
        <p class="forgot-password"><a href="#">Forgot password?</a></p>
        <button type="submit" class="login-button">Login</button>
        <p class="or-continue">or continue with</p>
        <button class="google-button">
          <i class="fab fa-google"></i>
        </button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: '',
      password: '',
      showPassword: false,
    };
  },
  methods: {
    togglePassword() {
      this.showPassword = !this.showPassword;
    },
    handleSubmit() {
      alert(`Logging in with ${this.email}`);
      // Handle login logic here
    },
  },
};
</script>

<style scoped>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Poppins', sans-serif;
  background-color: #111;
}

.container {
  display: flex;
  height: 100vh;
}

.left-side {
  width: 60%;
  background-color: #111;
  color: white;
  padding: 50px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.logo img {
  width: 150px;
}

.logo span {
  font-size: 14px;
  margin-top: 10px;
  color: white;
}

.content {
  margin-top: 100px;
}

.content h1 {
  font-size: 60px;
  padding-left: 120px;
  position: relative;
  top: 70px;
  color: white;
}

.content h2 {
  font-size: 30px;
  padding-left: 120px;
  margin-top: 10px;
  position: relative;
  top: 70px;
  color: white;
}

.highlight {
  color: #1a73e8;
}

.content p {
  margin-top: 10px;
  font-size: 20px;
  position: relative;
  top: 70px;
  padding-left: 120px;
}

.content a {
  color: #1a73e8;
  text-decoration: none;
}

.car img {
  width: 90%;
  padding-left:300px;
}

.right-side {
  width: 40%;
  background-color: #1b1b1b;
  padding: 100px 50px;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 15px;
}

.form {
  width: 100%;
}

h3 {
  font-size: 30px;
  color: white;
  margin-bottom: 20px;
}

.input-group {
  margin-bottom: 20px;
  position: relative;
}

.input-group input {
  width: 100%;
  padding: 15px;
  border: 1px solid #333;
  border-radius: 5px;
  background-color: #222;
  color: white;
  font-size: 16px;
}

.password-group {
  position: relative;
}

.eye-icon {
  position: absolute;
  right: 15px;
  top: 50%;
  transform: translateY(-50%);
  cursor: pointer;
  color: #ccc;
}

.forgot-password {
  text-align: right;
  margin-bottom: 20px;
}

.forgot-password a {
  font-size: 14px;
  color: #888;
}

.login-button {
  width: 100%;
  padding: 15px;
  border: none;
  border-radius: 5px;
  background-color: #1a73e8;
  color: white;
  font-size: 16px;
  cursor: pointer;
  margin-bottom: 20px;
}

.or-continue {
  text-align: center;
  color: #888;
  margin: 20px 0;
}

.google-button {
  width: 100%;
  padding: 15px;
  background-color: white;
  color: black;
  border: none;
  border-radius: 5px;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}

.google-button i {
  margin-right: 10px;
}
</style>
