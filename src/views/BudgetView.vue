<template>
    <div class="container">
        <h1>Budget Page</h1>
        <IncomeTable/>
        <ExpenseTable/> 
    </div>
    
</template>

<script>

import IncomeTable from '@/components/IncomeTable.vue'
import ExpenseTable from '@/components/ExpensesTable.vue'

export default{
components: {
    IncomeTable,
    ExpenseTable
}
}
</script>

<style scoped>
.container-fluid{
    padding-bottom: 1rem;
}
</style>