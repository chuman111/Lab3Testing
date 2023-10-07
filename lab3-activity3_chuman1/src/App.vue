<!--
  Title: App.Vue
  Author: Cody Human (Code based on sample code provided by ASU)
  Desc: Main app.vue file for activity 3
-->
<script>
import Balance from './components/Balance.vue'
import HelloWorld from './components/HelloWorld.vue'
import Currency from './components/Currency.vue'

export default {
  data() {
    return {
      fname: "Cody",
      bal: 100,
      amt: 10,
      denom: "INR"
    }
  },
  components: {
    Balance,
    HelloWorld,
    Currency
  }
}
</script>

<template>
  <header>
    <div>
      <!-- Added currency component and added emit/prop methods to update denom and amount -->
      <HelloWorld v-model:name="this.fname"/>
      <Balance @new-amt="(v) => this.amt=v" v-model:denomination="this.denom" />
      <Currency @new-denom="(v) => this.denom=v" v-model:amount="this.amt"/>
      </div>
  </header>
</template>

<style>

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 4);
  }
}
</style>
