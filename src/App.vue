<template>
  <div>
    <!-- the props: username and userage are created in ActiveUser.vue and they first get the default value from data() -> user {} -->
    <active-user
      :username="user.name"
      :userage="user.age"
      id="active-user"
    ></active-user>
    <user-data @set-data="setUserData"></user-data>
  </div>
</template>

<script>
export default {
  data() {
    return {
      //the defalt user that is displayed at page load
      user: {
        name: "Oana Nistor",
        age: 37,
      },
    };
  },

  methods: {
    //this method gets called at the custom event 'set-data', it gets the info that was sent with the event and uses it to create a new user object
    setUserData(enteredName, enteredAge) {
      this.user = {
        name: enteredName,
        age: enteredAge,
      };
    },
  },
};
</script>

<style>
html {
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  background-color: #efefef;
}

#active-user {
  text-align: center;
}

section {
  margin: 2rem auto;
  max-width: 40rem;
  border-radius: 12px;
  border: 1px solid #ccc;
  padding: 1rem;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  background-color: white;
}

#app button {
  font-size: smaller;
  font-weight: 700;
  cursor: pointer;
  border: 1px solid #ecf1ed;
  background-color: #292929;
  color: #2c2b2c;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
  border-radius: 5px;
  padding: 6px;
  color: white;
}

#app button:hover,
#app button:active {
  background-color: #db0c7e;
  border-color: #ecf1ed;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
  color: white;
}

#app input {
  font: inherit;
  padding: 0.25rem;
  margin-right: 20px;
}

#app input:hover,
#app input:focus {
  outline: none !important;
  border-color: #db0c7e;
  border-radius: 5px;
  box-shadow: 0 0 10px #719ece;
}
</style>
