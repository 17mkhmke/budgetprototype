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
            <tbody>
                <tr>
                    <td>ExpenseName</td>

                    <td>R</td>
                    <td><div class="btn-group">
                        <button class="btn btn-success">Edit</button>
                        <button class="btn btn-danger">Del</button>
                    </div></td>
                </tr>
            </tbody>
            <tfoot>
              <tr>
                <th>Savings</th>
              </tr>
              <tr>
                <td>R</td>
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
        <input type="text" placeholder="Expense Name">
        <input type="number" placeholder="Expense Amount">
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Save changes</button>
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
    name: 'ExpenseTable'
}
</script>