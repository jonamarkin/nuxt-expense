<template>
    <div class="flex flex-col items-center pt-20">
        <h1>Welcome to the Expenses Tracker</h1>
        <p class="text-neutral-500 dark:text-neutral-400">
            Track your expenses efficiently and effectively.
        </p>
        <TransactionCard category="Dining" :amount="22.50" type="debit" />

        <TransactionCard category="Transfer" :amount="150.00" type="credit" />
        <UButton color="primary">Button</UButton>
    </div>
</template>
