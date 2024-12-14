<template>
    <div class="card mt-4">
        <div class="card-header bg-success text-white">
            <h4>Add Transaction</h4>
        </div>
        <div class="card-body">
            <form @submit.prevent="addTransaction">
                <div class="form-group mb-3">
                    <label for="text" class="text-success">Transaction Description</label>
                    <input type="text" id="text" class="form-control" v-model="transactionText" required />
                </div>
                <div class="form-group mb-3">
                    <label for="amount" class="text-success">Amount (negative - expense, positive - income)</label>
                    <input type="number" id="amount" class="form-control" v-model.number="transactionAmount" required />
                </div>
                <button type="submit" class="btn btn-success w-100">Add Transaction</button>
            </form>
        </div>
    </div>
</template>

<script setup>
import { ref, defineEmits } from 'vue';

const transactionText = ref('');
const transactionAmount = ref(0);
const emit = defineEmits(['add-transaction']);

const addTransaction = () => {
    if (!transactionText.value.trim() || transactionAmount.value === 0) {
        alert('Please enter valid transaction details.');
        return;
    }

    const newTransaction = {
        text: transactionText.value,
        amount: transactionAmount.value,
    };

    // Emit the new transaction to the parent component
    emit('add-transaction', newTransaction);

    // Clear inputs after submission
    transactionText.value = '';
    transactionAmount.value = 0;
};
</script>

