<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      email: 'example@google.com',
      password: '123456',
    }
  },
  methods: {
    emailInput(value) {
      this.email = value;
      console.log(this.email);
    },
    passwordInput(value) {
      this.password = value;
      console.log(this.password);
    },
  }
}
</script>


<template>
  <div class="hello">
    <label>
      Enter e-mail:
        <input
          type="email"
          :placeholder="email"
          @input="emailInput($event.target.value)"
        />
    </label>
    <label>
      Enter password:
        <input
          type="password"
          :placeholder="password"
          @input="passwordInput($event.target.value)"
        />
    </label>
  </div>
</template>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
