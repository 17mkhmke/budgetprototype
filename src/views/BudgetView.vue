<template>
    <div class="container">
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
    padding-bottom: 2rem;
}
</style>