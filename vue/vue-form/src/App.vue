<template>
  <form>
    <div>
      <label for="username">id:</label>
      <input type="text" id="username" v-model="username" />
    </div>
    <div>
      <label for="password">password :</label>
      <input type="text" id="password" v-model="password" />
    </div>
    <button type="submit" v-on:click.prevent="submitForm">login</button>
  </form>
</template>

<script>
import axios from 'axios';

export default {
  data: function() {
    return {
      username: '',
      password: '',
    };
  },
  methods: {
    submitForm: function() {
      // e.preventDefault();
      console.log(this.username, this.password);
      const axiosData = {
        url: 'https://jsonplaceholder.typicode.com/users',
        data: {
          username: this.username,
          password: this.password,
        },
      };
      axios
        .post(axiosData.url, axiosData.data)
        .then((res) => console.log(res))
        .catch((error) => console.log(error));
    },
  },
};
</script>

<style></style>
