<!-- TransactionList.vue -->
<template>
    <div class="card mt-4">
        <div class="card-header bg-success text-white">
            <h4>Transaction List</h4>
        </div>
        <ul class="list-group list-group-flush">
            <li v-for="transaction in transactions" :key="transaction.id"
                :class="transaction.amount < 0 ? 'minus' : 'plus'"
                class="list-group-item d-flex justify-content-between align-items-center bg-light">
                {{ transaction.text }}
                <span class="text-danger">{{ transaction.amount }}</span>
                <button class="btn btn-danger btn-sm">&times;</button>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    data() {
        return {
            transactions: [
                { id: 1, text: 'Food', amount: -199.00 },
                { id: 2, text: 'Salary', amount: 3499.00 },
                { id: 3, text: 'Transport', amount: -300.00 },
                { id: 4, text: 'Transport', amount: -499.00 },
            ]
        }
    }
}
</script>