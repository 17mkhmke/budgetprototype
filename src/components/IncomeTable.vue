<template>
    <div class="container-fluid">
        <h1>Income Table</h1>
        <table class="table table-striped table-hover">
            <thead>
                <tr>
                    <th>Name</th>
                    <th>Amount</th>
                    <th>Edit & Del</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="income in userIncome" :key="income">
                    <td>{{ income.name }}</td>
                    <td>R{{ income.amount }}</td>
                    <td><div class="btn-group">
                        <!-- Button trigger modal -->
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#editModal">
  Edit
</button>

<!-- Modal -->
<div class="modal fade" id="editModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h1 class="modal-title fs-5" id="exampleModalLabel">Edit This Income:</h1>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        <input class="form-control text-center" type="text" placeholder="New Name" required>

        <input class="form-control text-center" type="number" placeholder="New Amount" required>

      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary" data-bs-dismiss="modal">Save changes</button>
      </div>
    </div>
  </div>
</div>
                        <button class="btn btn-danger" v-on:click="removeIncome(income)">Del</button>
                    </div>
                  </td>
                </tr>
            </tbody>
            <tfoot>
              <tr>
                <th class="bg-transparent border-0"></th>
                <th class="bg-transparent border-0"></th>
                <th>Total Income</th>
              </tr>
              <tr>
                <td class="bg-transparent border-0"></td>
                <td class="bg-transparent border-0"></td>
                <td>R{{ totalIncome }}</td>
              </tr>
            </tfoot>
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
        <input class="form-control text-center newIncomeName" type="text" placeholder="Income Name" required>

        <input class="form-control text-center newIncomeAmount" type="number" placeholder="Income Amount" required>

      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary" data-bs-dismiss="modal" v-on:click="addIncome">Save changes</button>
      </div>
    </div>
  </div>
</div>

    </div>
</template>


<script>
export default{
    name: 'IncomeTable',
    data: function(){
      return{
      userIncome:JSON.parse(localStorage.getItem('userIncome')),
      totalIncome:parseInt(JSON.parse(localStorage.getItem('userSalary')))
      }},
    methods:{
      addIncome(){
        let newName=document.querySelector('.newIncomeName').value
        let newAmount=document.querySelector('.newIncomeAmount').value
        this.totalIncome+=parseInt(newAmount)
        this.userIncome.push({
          name: newName,
          amount: newAmount
        })
        localStorage.setItem('userSalary', JSON.stringify(this.totalIncome))
        localStorage.setItem('userIncome',JSON.stringify(this.userIncome))
        location.reload()
      },
      removeIncome(income){
        this.totalIncome=this.totalIncome-parseInt(income.amount)
        this.userIncome.splice(this.userIncome.indexOf(income),1)
        localStorage.setItem('userSalary',JSON.stringify(this.totalIncome))
        localStorage.setItem('userIncome', JSON.stringify(this.userIncome))
        location.reload()
      }
    },
    mounted(){
      localStorage.setItem('userSalary',JSON.stringify(this.totalIncome))
    }
}
</script>

<style scoped>
.container-fluid{
    margin-bottom: 5rem;
}
</style>