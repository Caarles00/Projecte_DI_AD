<template>
    <q-page-container>
        <!-- https://codingpotions.com/vue-login -->
        <div class="register">
            <h1 class="title">Register</h1>
            <form action class="form" @submit.prevent="register">
                <label class="form-label" for="#fullName">Name:</label>
                <input
                    v-model="fullName"
                    class="form-input"
                    type="fullName"
                    id="fullName"
                    required
                    placeholder="Full Name"
                >
                <label class="form-label" for="#dni">DNI:</label>
                <input
                    v-model="dni"
                    class="form-input"
                    type="dni"
                    id="dni"
                    required
                    placeholder="DNI"
                >
                <label class="form-label" for="#username">Userame:</label>
                <input
                    v-model="username"
                    class="form-input"
                    type="username"
                    id="username"
                    required
                    placeholder="Username"
                >
                <label class="form-label" for="#password">Password:</label>
                <input
                    v-model="password"
                    class="form-input"
                    type="password"
                    id="password"
                    placeholder="Password"
                >
                <label class="form-label" for="#password-repeat">Repetix la contrasenya:</label>
                <input
                    v-model="passwordRepeat"
                    class="form-input"
                    type="password"
                    id="password-repeat"
                    placeholder="Password"
                >
                <input class="form-submit" type="submit" value="Registra't">
                <p class="msg">Ja estas registrat?
                  <a href="http://localhost:8080/#/login">Login</a>
                </p>
            </form>
        </div>
    </q-page-container>
</template>

<script>
export default {
  name: 'Register'
}
</script>

<style lang="scss" scoped>
.register {
  padding: 2rem;
}
.title {
  text-align: center;
}
.form {
  margin: 3rem auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 20%;
  min-width: 350px;
  max-width: 100%;
  background: rgba(19, 35, 47, 0.9);
  border-radius: 5px;
  padding: 40px;
  box-shadow: 0 4px 10px 4px rgba(0, 0, 0, 0.3);
}
.form-label {
  margin-top: 2rem;
  color: white;
  margin-bottom: 0.5rem;
  &:first-of-type {
    margin-top: 0rem;
  }
}
.form-input {
  padding: 10px 15px;
  background: none;
  background-image: none;
  border: 1px solid white;
  color: white;
  &:focus {
    outline: 0;
    border-color: #3073f0;
  }
}
.form-submit {
  background: #3073f0;
  border: none;
  color: white;
  margin-top: 3rem;
  padding: 1rem 0;
  cursor: pointer;
  transition: background 0.2s;
  &:hover {
    background: #0b9185;
  }
}
.msg {
  margin-top: 1rem;
  text-align: center;
  color: white;
}

</style>