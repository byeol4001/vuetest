<template>
  <div>
    <app-header v-bind:propsdata="text" v-on:renew="renewStr" />
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue';
export default {
  data: function() {
    return {
      text: 'header',
    };
  },
  components: {
    AppHeader,
  },
  methods: {
    renewStr: function() {
      this.text = 'hi';
    },
  },
};
</script>

<style></style>
