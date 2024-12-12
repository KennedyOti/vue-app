<!-- AddTransaction.vue -->
<template>
    <div class="card mt-4">
        <div class="card-header bg-success text-white">
            <h4>Add Transaction</h4>
        </div>
        <div class="card-body">
            <form>
                <div class="form-group mb-3">
                    <label for="text" class="text-success">Transaction Description</label>
                    <input type="text" id="text" class="form-control" required />
                </div>
                <div class="form-group mb-3">
                    <label for="amount" class="text-success">Amount (negative - expense, positive - income)</label>
                    <input type="number" id="amount" class="form-control" required />
                </div>
                <button type="submit" class="btn btn-success w-100">Add Transaction</button>
            </form>
        </div>
    </div>
</template>