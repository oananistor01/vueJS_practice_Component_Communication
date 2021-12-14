<template>
  <section>
    <h2>{{ username }}</h2>
    <h3>{{ userage }} years and fabulous</h3>
  </section>
</template>

<script>
export default {
  //create props, custom attributes for the parent component App.vue to use them
  props: ["username", "userage"],

  // props: {
  //   username: {
  //     type: String,
  //     required: true
  //   },
  //   userage: {
  //     type: Number,
  //     required: true
  //   }
  // }
};
</script>
