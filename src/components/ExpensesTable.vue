<template>
    <div class="container-fluid">
        <h1>Expenses & Savings Table</h1>
        <table class="table table-success table-hover">
            <thead>
                <tr>
                    <th>Name</th>
                    <th>Percentage</th>
                    <th>Amount</th>
                    <th>Edit & Del</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>ExpenseName</td>
                    <td>%</td>
                    <td>R</td>
                    <td><div class="btn-group">
                        <button class="btn btn-success">Edit</button>
                        <button class="btn btn-danger">Del</button>
                    </div></td>
                </tr>
            </tbody>
            <tfoot></tfoot>
        </table>
        <!-- Button trigger modal -->
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
  ADD EXPENSE
</button>

<!-- Modal -->
<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h1 class="modal-title fs-5" id="exampleModalLabel">Declare an Expense</h1>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Ea atque reprehenderit ratione eos aliquid quia saepe fugiat adipisci, neque libero, animi alias accusamus dolores consectetur maiores eaque quas, dicta soluta?
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