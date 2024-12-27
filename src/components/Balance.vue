<template>
    <div class="card mt-4">
        <div class="card-header bg-success text-white">
            <h4>Your Balance</h4>
        </div>
        <div class="card-body text-center">
            <h1 class="text-success">KSH{{ balance }}</h1>
        </div>
    </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
    balance: {
        type: Number,
        required: true,
    }
});
</script>
