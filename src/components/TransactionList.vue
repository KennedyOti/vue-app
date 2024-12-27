<template>
    <div class="card mt-4">
        <div class="card-header bg-success text-white">
            <h4>Transaction List</h4>
        </div>
        <ul class="list-group list-group-flush">
            <li v-for="transaction in transactions" :key="transaction.id"
                class="list-group-item d-flex justify-content-between align-items-center bg-light">
                {{ transaction.text }}
                <span :class="transaction.amount > 0 ? 'text-success' : 'text-danger'">
                    KSH{{ transaction.amount }}
                </span>
                <button class="btn btn-danger btn-sm"
                    @click="$emit('delete-transaction', transaction.id)">&times;</button>
            </li>
        </ul>
    </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
    transactions: {
        type: Array,
        required: true,
    }
});
</script>
