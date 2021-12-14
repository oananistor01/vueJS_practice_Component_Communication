<template>
  <section>
    <form @submit.prevent="setData">
      <!-- when the button is clicked, it automatically submits the form, because of the <form> element being used here  -->
      <input type="text" placeholder="Your name" v-model="enteredName" />
      <input type="text" placeholder="Your age" v-model="enteredAge" />
      <button>Set Data</button>
    </form>
  </section>
</template>

<script>
export default {
  //we store here the emits created
  emits: ["set-data"],

  //listen to what is entered in the input fields and send it to parent component App.vue for displaying it
  data() {
    return {
      enteredName: "",
      enteredAge: "",
    };
  },

  methods: {
    setData() {
      //create a custom event called 'set-data', and send the input data alltogether
      this.$emit("set-data", this.enteredName, this.enteredAge);
    },
  },
};
</script>
