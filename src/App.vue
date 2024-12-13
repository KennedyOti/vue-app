<template>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.1/dist/css/bootstrap.min.css" rel="stylesheet">
  <div id="app">
    <Header />
    <div class="container mt-4">
      <Balance :total="total" />
      <IncomeExpense :income="income" :expenses="expenses" />
      <TransactionList :transactions="transactions" />
      <AddTransaction />
    </div>
  </div>
</template>

<script setup>
import AddTransaction from './components/AddTransaction.vue';
import Balance from './components/Balance.vue';
import Header from './components/Header.vue';
import IncomeExpense from './components/IncomeExpense.vue';
import TransactionList from './components/TransactionList.vue';

import { ref, computed } from 'vue';

const transactions = ref([
  { id: 1, text: 'Food', amount: -199.00 },
  { id: 2, text: 'Salary', amount: 3499.00 },
  { id: 3, text: 'Transport', amount: -300.00 },
  { id: 4, text: 'Transport', amount: -499.00 },
]);

// Get total 
const total = computed(() => {
  return transactions.value.reduce((acc, transaction) => {
    return acc + transaction.amount;
  }, 0);
})

// Get Income
const income = computed(() => {
  return transactions.value
    .filter((transaction) => transaction.amount > 0) // Corrected `transaction.amount`
    .reduce((acc, transaction) => {
      return acc + transaction.amount;
    }, 0)
    .toFixed(2);
});

// Get Expenses
const expenses = computed(() => {
  return transactions.value
    .filter((transaction) => transaction.amount < 0) // Corrected `transaction.amount`
    .reduce((acc, transaction) => {
      return acc + transaction.amount;
    }, 0)
    .toFixed(2);
});


</script>
