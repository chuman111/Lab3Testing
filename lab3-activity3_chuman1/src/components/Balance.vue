<!--
  Title: Balance.Vue
  Author: Cody Human (Code based on sample code provided by ASU)
  Desc: Balance.vue file for activity 3
-->
<script>
export default {
    name: 'Balance',
    data() {
        return {
            balance: 100,
            amount: 10,
        }
    },
    props: {
      denomination: String
    },
    emits: ['newBal', 'newAmt'], 
    computed: {
        balanceString() {
            return `Account Balance: ${this.balance}`;
        }
    },
    methods: {
        addBalance() {
            this.balance += this.amount
            this.$emit('newBal', this.balance);
            //this.amount = 0;
        },
        subtractBalance() {
            this.balance -= this.amount
            //this.amount = 0;
        },
        //Added emit method to update amount value for Currency.vue. Requirement R5
        updateAmt() {
          this.$emit('newAmt', this.amount)
        }
    },
    mounted() {
        console.log('Application mounted');
    },
}
</script>

<template>
    <div class="greetings">
      <h3>{{balanceString}} {{ denomination }}, Amount: {{ amount }} {{ denomination }}</h3>
      <label for="range">Change Amount to:</label>
      <!-- calls updateAmt on value change. Requirements R2 and R4-->
      <input @change="updateAmt" v-model.number="amount" name="range" type="range" min="0" max="100" step="5"/>
      <div>
      <button @click="addBalance">Add</button>
      <!-- Hides subtract button if amount is greater than balance. Requirement R3-->
      <button v-if="amount <= balance" @click="subtractBalance">Subtract</button>
      </div>
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