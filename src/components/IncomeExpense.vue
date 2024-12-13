<!-- IncomeExpense.vue -->
<template>
    <div class="card mt-4">
        <div class="card-body d-flex justify-content-around">
            <div>
                <h5 class="text-success">Income</h5>
                <p class="text-success">${{ income }}</p>
            </div>
            <div>
                <h5 class="text-danger">Expense</h5>
                <p class="text-danger">${{ expenses }}</p>
            </div>
        </div>
    </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
    income: {
        type: Number,
        required: true
    },
    expenses: {
        type: Number,
        required: true
    }
});
</script>