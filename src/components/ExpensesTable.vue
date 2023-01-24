<template>
    <div class="container-fluid">
        <h1>Expenses & Savings Table</h1>
        <table class="table table-success table-hover">
            <thead>
                <tr>
                    <th>Name</th>

                    <th>Amount</th>
                    <th>Edit & Del</th>
                </tr>
            </thead>
            <tbody class="mb-5">
                <tr v-for="expense in userExpense" :key="expense">
                    <td>{{ expense.name }}</td>

                    <td>R{{ expense.amount }}</td>
                    <td><div class="btn-group">
                     <!-- Button trigger modal -->
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#editExpenseModal">
  Edit
</button>

<!-- Modal -->
<div class="modal fade" id="editExpenseModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h1 class="modal-title fs-5" id="exampleModalLabel">Edit This Expense:</h1>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        <input class="form-control text-center newExpenseName" type="text" placeholder="New Name" required>

        <input class="form-control text-center newExpenseAmount" type="number" placeholder="New Amount" required>

      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary" data-bs-dismiss="modal">Save changes</button>
      </div>
    </div>
  </div>
</div>
                        <button class="btn btn-danger">Del</button>
                    </div></td>
                </tr>
            </tbody>
            <tfoot>
              <tr>
                <th class="bg-transparent border-0"></th>
                <th class="bg-transparent border-0"></th>
                <th>Savings</th>
              </tr>
              <tr>
                <td class="bg-transparent border-0"></td>
                <td class="bg-transparent border-0"></td>
                <td>R{{ totalIncome-totalExpenses }}</td>
              </tr>
            </tfoot>
        </table>
        <!-- Button trigger modal -->
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#expenseModal">
  ADD EXPENSE
</button>

<!-- Modal -->
<div class="modal fade" id="expenseModal" tabindex="-1" aria-labelledby="expenseModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h1 class="modal-title fs-5" id="expenseModalLabel">Declare an Expense</h1>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        <input class="form-control newExpenseName" type="text" placeholder="Expense Name">
        <input class="form-control newExpenseAmount" type="number" placeholder="Expense Amount">
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary" data-bs-dismiss="modal" v-on:click="addExpense">Save changes</button>
      </div>
    </div>
  </div>
</div>
    </div>
</template>

<style scoped>

</style>

<script>
export default{
    name: 'ExpenseTable',
    data: function(){
      return{
        userExpense:[],
        totalExpenses:0,
        totalIncome:JSON.parse(localStorage.getItem('userSalary'))
      }
    },
    methods:{
      addExpense(){
        let newExpenseName = document.querySelector('.newExpenseName').value
        let newExpenseAmount = document.querySelector('.newExpenseAmount').value
        this.totalIncome+= -newExpenseAmount
        console.log(totalIncome)
        this.userExpense.push({
          name: newExpenseName,
          amount: newExpenseAmount
        })
        document.querySelector('.newExpenseName').value=''
        document.querySelector('.newExpenseAmount').value=''
      }
    }
}
</script>