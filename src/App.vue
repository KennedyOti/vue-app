<template>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.1/dist/css/bootstrap.min.css" rel="stylesheet">
  <div id="app">
    <Header />
    <div class="container mt-4">
      <Balance />
      <IncomeExpense />
      <TransactionList />
      <AddTransaction />
    </div>
  </div>
</template>

<script>
import AddTransaction from './components/AddTransaction.vue';
import Balance from './components/Balance.vue';
import Header from './components/Header.vue';
import IncomeExpense from './components/IncomeExpense.vue';
import TransactionList from './components/TransactionList.vue';

export default {
  components: {
    AddTransaction,
    Balance,
    Header,
    IncomeExpense,
    TransactionList,
  },
};
</script>
