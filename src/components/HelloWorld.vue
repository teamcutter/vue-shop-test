<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      email: 'example@google.com',
      password: '123456',
      loginList: [
        {
          email: 'SomeEmlail'
        },
        {
          email: 'SomeEmlail2'
        },
        {
          email: 'SomeEmlail3'
        }
      ],
      pages: 3,
      currentPage: 1,
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
    loadLogins(page) {
      console.log(`Загрузка логинов, страница - ${page}`)
    }
  },
  computed: {
    getEmailAndPassword() {
      return `${this.email} ${this.password}`;
    }
  },
  watch: {
    currentPage(page){
      this.loadLogins(page);
    }
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
    <h1>
      {{ getEmailAndPassword }}
    </h1>
    <ul>
      <li v-for="(login, index) in loginList"
      :key="index">
        {{ login.email }}
      </li>
    </ul>
    <button
        type="button"
        @click="currentPage--"
      >
        Prev.
      </button>
      <button
        type="button"
        v-for="page in pages"
        :key="page"
        @click="currentPage = page"
      >
        {{ page }}
      </button>
      <button
        type="button"
        @click="currentPage++"
      >
        Next.
      </button>
      <p>Page: {{ currentPage }} / {{ pages }}</p>

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
