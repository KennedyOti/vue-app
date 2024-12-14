<template>
    <div class="row text-center mt-4">
        <div class="col-md-6">
            <div class="card border-success mb-3">
                <div class="card-header bg-success text-white">Income</div>
                <div class="card-body text-success">
                    <h5 class="card-title">{{ income }}</h5>
                </div>
            </div>
        </div>
        <div class="col-md-6">
            <div class="card border-danger mb-3">
                <div class="card-header bg-danger text-white">Expenses</div>
                <div class="card-body text-danger">
                    <h5 class="card-title">{{ Math.abs(expenses) }}</h5>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
    income: {
        type: Number,
        required: true,
    },
    expenses: {
        type: Number,
        required: true,
    }
});
</script>
