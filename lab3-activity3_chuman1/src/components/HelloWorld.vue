<!--
  Title: Currency.Vue
  Author: Cody Human (Code based on sample code provided by ASU)
  Desc: Provides the Hello <name> header for Activity. 
  Note: No modification was made from HelloWorld.vue that was
   cloned from SER421 Git repo.
-->
<script>
  export default {
    name: 'HelloWorld',
    props: {
      name: String
    },
    data() {
        return {
            msg: "Hello ",
            amt: 25
        }
    },
  }
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }} {{name}}</h1>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
