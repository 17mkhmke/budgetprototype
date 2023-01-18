<template>
    <div class="container-fluid">
        <h1>Income Table</h1>
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
                    <td>IncomeName</td>
                    <td>%</td>
                    <td>R</td>
                    <td><div class="btn-group">
                        <button class="btn btn-success">Edit</button>
                        <button class="btn btn-danger">Del</button>
                    </div></td>
                </tr>
            </tbody>
        </table>
        <!-- Button trigger modal -->
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
  ADD INCOME STREAM
</button>

<!-- Modal -->
<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h1 class="modal-title fs-5" id="exampleModalLabel">Declare your Income</h1>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Optio esse at perspiciatis laudantium qui, molestias minus provident quis quas quae temporibus sequi ipsa tenetur est iure ipsum beatae commodi porro.
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


<script>
export default{
    name: 'IncomeTable'
}
</script>

<style scoped>
.container-fluid{
    margin-bottom: 5rem;
}
</style>