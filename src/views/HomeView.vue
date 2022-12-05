<!-- eslint-disable vuejs-accessibility/label-has-for -->
<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>

    <v-form @submit="onSubmit" v-slot="{ errors, values, validate }">
      {{ errors }} {{ values }}
    <div class="mb-3">
      <label for="email" class="form-label">Email</label>
      <v-field id="email" name="email" type="email" class="form-control" rules="email|required"
      :class="{ 'is-invalid': errors['email'] }"
      v-model="user.email"
      placeholder="請輸入 Email"></v-field>
      <error-message class="invalid-feedback" name="email"></error-message>
    </div>

    <button class="btn btn-primary" type="button" @click="validate">驗證</button>
    <button class="btn btn-primary" type="submit">Submit</button>
  </v-form>

  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue';

export default {
  name: 'HomeView',
  components: {
    HelloWorld,
  },
  data() {
    return {
      user: {},
    };
  },
  methods: {
    onSubmit() {
      console.log(this.user);
    },
    // isPhone(value) {
    //   const phoneNumber = /^(09)[0-9]{8}$/
    //   return phoneNumber.test(value) ? true : '需要正確的電話號碼'
    // },
  },
  created() {
    console.log(this);
  },
};
</script>
