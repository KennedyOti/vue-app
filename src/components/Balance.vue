<!-- Balance.vue -->
<template>
    <div class="card text-center bg-dark text-white">
        <div class="card-body">
            <h4 class="text-success">Your Balance</h4>
            <h1>${{ total }}</h1>
        </div>
    </div>
</template>

<script setup>
import { defineProps } from 'vue';
const props = defineProps({
    total: {
        type: Number,
        required: true,
    },
});
</script>