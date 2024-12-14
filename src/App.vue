<template>
  <div class="container mt-4">
    <Header />
    <Balance :balance="balance" />
    <IncomeExpense :income="income" :expenses="expenses" />
    <TransactionList :transactions="transactions" @delete-transaction="deleteTransaction" />
    <AddTransaction @add-transaction="addTransaction" />
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';
import Header from './components/Header.vue';
import Balance from './components/Balance.vue';
import IncomeExpense from './components/IncomeExpense.vue';
import TransactionList from './components/TransactionList.vue';
import AddTransaction from './components/AddTransaction.vue';

const transactions = ref([]);

const balance = computed(() => {
  return transactions.value.reduce((acc, transaction) => acc + transaction.amount, 0);
});

const income = computed(() => {
  return transactions.value
    .filter(transaction => transaction.amount > 0)
    .reduce((acc, transaction) => acc + transaction.amount, 0);
});

const expenses = computed(() => {
  return transactions.value
    .filter(transaction => transaction.amount < 0)
    .reduce((acc, transaction) => acc + transaction.amount, 0);
});

const addTransaction = (newTransaction) => {
  transactions.value.push({ ...newTransaction, id: Date.now() });
};

const deleteTransaction = (id) => {
  transactions.value = transactions.value.filter(transaction => transaction.id !== id);
};
</script>
