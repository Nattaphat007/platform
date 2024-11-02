<template>
  <div class="container">
    <div class="left-section">
      <div class="logo">
        <img src="@/assets/logo.png" alt="EasyMiles" />
        <span>CAR RENTAL</span>
      </div>
      <div class="content">
        <h1>Sign Up to</h1>
        <h2><span class="highlight">EasyMiles</span> Easy Way to Rent</h2>
        <p class="login-info">If you already have an account</p>
        <p class="login-link">
          You can <router-link to="/">Login here !</router-link>
        </p>
      </div>
      <div class="car">
        <img src="@/assets/car.png" alt="Car" />
      </div>
    </div>
    <div class="right-section">
      <h2 class="title">Sign Up</h2>
      <form class="form" @submit.prevent="handleSubmit">
        <div class="input-group">
          <label for="email">Enter Email</label>
          <input type="email" id="email" placeholder="Enter your email" v-model="email" required />
        </div>
        <div class="input-group">
          <label for="username">Create User name</label>
          <input type="text" id="username" placeholder="Create a user name" v-model="username" required />
        </div>
        <div class="input-group">
          <label for="contact">Contact number</label>
          <input type="text" id="contact" placeholder="Enter your contact number" v-model="contact" required />
        </div>
        <div class="input-group password-group">
          <label for="password">Password</label>
          <input :type="showPassword ? 'text' : 'password'" id="password" v-model="password" placeholder="Enter your password" required />
          <span class="eye-icon" @click="togglePassword">
            <i :class="showPassword ? 'fas fa-eye-slash' : 'fas fa-eye'"></i>
          </span>
        </div>
        <div class="input-group password-group">
          <label for="confirm-password">Confirm Password</label>
          <input :type="showPassword ? 'text' : 'password'" id="confirm-password" v-model="confirmPassword" placeholder="Confirm your password" required />
          <span class="eye-icon" @click="togglePassword">
            <i :class="showPassword ? 'fas fa-eye-slash' : 'fas fa-eye'"></i>
          </span>
        </div>
        <button type="submit" class="register-button">Register</button>
        <p class="or-continue">or continue with</p>
        <div class="social-login">
          <button class="google-button">
            <i class="fab fa-google"></i> Continue with Google
          </button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: '',
      username: '',
      contact: '',
      password: '',
      confirmPassword: '',
      showPassword: false,
    };
  },
  methods: {
    togglePassword() {
      this.showPassword = !this.showPassword;
    },
    handleSubmit() {
      alert(`Registered with email: ${this.email}`);
      // Handle the form submission logic here
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
  background: linear-gradient(135deg, #111, #222);
}

.left-section {
  width: 60%;
  padding: 50px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  color: white;
}

.logo img {
  width: 150px;
}

.logo span {
  font-size: 14px;
  margin-top: 10px;
  color: white;
}

.content h1 {
  font-size: 60px;
  color: white;
}

.content h2 {
  font-size: 30px;
  color: #1a73e8;
}

.highlight {
  color: #4e97d8;
}

.login-link a {
  color: #1a73e8;
  text-decoration: none;
}

.car img {
  width: 90%;
}

.right-section {
  width: 40%;
  background-color: #1b1b1b;
  padding: 50px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  border-radius: 10px;
  box-shadow: 0 0 15px rgba(0, 0, 0, 0.3);
}

.title {
  font-size: 36px;
  margin-bottom: 20px;
  color: white;
}

.form {
  width: 100%;
}

.input-group {
  margin-bottom: 20px;
  position: relative;
}

.input-group label {
  display: block;
  font-size: 14px;
  color: #ddd;
  margin-bottom: 5px;
}

.input-group input {
  width: 100%;
  padding: 15px;
  border: 1px solid #333;
  border-radius: 5px;
  background-color: #222;
  color: white;
}

.password-group .eye-icon {
  position: absolute;
  right: 15px;
  top: 50%;
  transform: translateY(-50%);
  cursor: pointer;
  color: #ccc;
}

.register-button {
  width: 100%;
  padding: 15px;
  border: none;
  border-radius: 5px;
  background: linear-gradient(90deg, #1a73e8, #4e97d8);
  color: white;
  font-size: 16px;
  cursor: pointer;
  transition: 0.3s ease;
}

.register-button:hover {
  background: linear-gradient(90deg, #4e97d8, #1a73e8);
}

.or-continue {
  color: #aaa;
  text-align: center;
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

.google-button:hover {
  background-color: #eee;
}
</style>
