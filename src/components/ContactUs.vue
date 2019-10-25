<template>
  <div>
    <form id="app" @submit="checkForm" action="http://httpbin.org/post" method="post" novalidate="true">
      <div v-if="errors.length">
        <b>Error</b>
        <ul>
          <li v-for="(error, index) in errors" :key="index">{{ error }}</li>
        </ul>
      </div>
      <br />

      <label for="name">Имя</label>
      <input
        id="name"
        v-model="name"
        type="text"
        name="name"
        maxlength="30"
        v-bind:class="{ inputerror: errorStyleName }"
      />
      <br />

      <label for="email">Email</label>
      <input
        id="email"
        v-model="email"
        type="email"
        name="email"
        v-bind:class="{ inputerror: errorStyleEmail }"
      />
      <br />

      <label for="phone">Phone</label>
      <input
        id="phone"
        v-model="phone"
        type="tel"
        name="phone"
        v-bind:class="{ inputerror: errorStylePhone }"
      />
      <br />

      <input type="submit" value="Отправить" v-bind:class="{ sub: button }" />
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      errors: [],
      name: null,
      email: null,
      phone: null,
      button: false,
      errorStyleName: false,
      errorStyleEmail: false,
      errorStylePhone: false
    }
  },
  methods: {
    checkForm: function (e) {

      this.errors = [];

      if (this.name) {
        this.errorStyleName = false;
        this.ttt = false
      }

      if (this.email) {
        this.errorStyleEmail = false;
        this.ttt = false
      }

      if (this.phone) {
        this.errorStylePhone = false;
        this.ttt = false
      }

      if (!this.name) {
        this.errors.push('Форма с именем не должна быть пустой');
        this.errorStyleName = true;
      }

      if (!this.validName(this.name)) {
        this.errors.push('Форма с именем должна содержать буквы и пробелы');
        this.errorStyleName = true;
      }

      if (!this.email) {
        this.errors.push('Форма с почтой не должна быть пустой');
        this.errorStyleEmail = true;
      }

      if (!this.validEmail(this.email)) {
        this.errors.push('Адресс должен содержать <name>@<name>.<domen>');
        this.errorStyleEmail = true;
      }

      if (!this.phone) {
        this.errors.push('Форма с телефоном не может быть пустой');
        this.errorStylePhone = true;
      }

      if (!this.validPhone(this.phone)) {
        this.errors.push('Укажите корректный телефон начиная с +38093 и содержать 7 цифр.');
        this.errorStylePhone = true;
      }

      if (!this.errors.length) {
        this.button = true;
        return true;
      }

      e.preventDefault();
    },
    validName: function (name) {
      var re = /^[a-zA-ZА-Яа-яЁё\s]*$/;
      return re.test(name);
    },
    validEmail: function (email) {
      var re = /\S+@\S+\.\S+/;
      return re.test(email);
    },
    validPhone: function (phone) {
      var re = /\+38093\d{7}/;
      return re.test(phone);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.sub {
  color: red;
}
.inputerror {
  border: 1px solid red;
}
</style>