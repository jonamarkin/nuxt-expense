<template>
    <UCard class="relative flex items-center px-4 py-2 w-80">
        <!--Content of the card-->
        <div class="flex justify-between w-full">
            <!-- Category -->
            <span class="text-sm font-medium text-gray-800 dark:text-white">
                {{ category }}
            </span>

            <!-- Amount -->
            <span class="text-sm font-semibold text-gray-700 dark:text-gray-200">
                {{ formattedAmount }}
            </span>
        </div>
        <!-- Colored Edge -->
        <div class="absolute top-0 right-0 h-full w-1 rounded-r" :class="{
            'bg-green-500': type === 'credit',
            'bg-red-500': type === 'debit',
        }" />
    </UCard>
</template>

<script setup>
const props = defineProps({
    category: {
        type: String,
        required: true,
    },
    amount: {
        type: Number,
        required: true,
    },
    type: {
        type: String,
        required: true,
        validator: (value) => ['credit', 'debit'].includes(value),
    },
});

const formattedAmount = new Intl.NumberFormat('en-US', {
    style: 'currency',
    currency: 'USD',
}).format(props.amount);

</script>