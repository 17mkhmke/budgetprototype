<template>
    <div class="container-fluid">
        <h1>Income Table</h1>
        <table class="table table-success table-hover">
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
                        <button class="btn btn-success">Edit</button>
                        <button class="btn btn-danger">Del</button>
                    </div>
                  </td>
                </tr>
            </tbody>
            <tfoot>
              <tr>
                <th>Total Income</th>
              </tr>
              <tr>
                <td>R</td>
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
        <input class="form-control text-center newIncomeName" type="text" placeholder="Income Name">
        <input class="form-control text-center newIncomeAmount" type="number" placeholder="Income Amount">
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary" v-on:click="addIncome">Save changes</button>
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
      userIncome:[{
        name: 'Total Salary',
        amount: JSON.parse(localStorage.getItem('userIncome'))
      }]
      }},
      function(){
        let userTotalIncome=[]
        this.userIncome.forEach(item => {
        userTotalIncome.push(item.amount)
        })
        return{
          userTotalIncome
        }
      },
    methods:{
      addIncome(){
        // userIncome.push({
        //   name: document.querySelector('.newIncomeName'),
        //   amount: document.querySelector('.newIncomeAmount')
        // });
        // localStorage.setItem('userIncome', JSON.stringify(this.userIncome))
        console.log(this.userTotalIncome)
      }
    }

}
</script>

<style scoped>
.container-fluid{
    margin-bottom: 5rem;
}
</style>