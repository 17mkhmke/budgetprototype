<template>
  <div class="container-fluid">
    <h1 class="display-5">Big Budget Corporation &copy;</h1>
    <div class="flip-card">
                <figure class="flip-card-inner">
                  <div class="flip-card-front">
                    <h2 class="lead">Welcome To The BBC!</h2>
                    <p>We are a company dedicated to educating and aiding people with budgeting.</p>
                    <button class="btn btn-primary">Sign Up</button>
                  </div>

                  <div class="flip-card-back d-flex flex-column">
                    <p>Please fill out our basic form:</p>
                    <form action="">
                    <input class="form-control mb-1 text-center" type="text" name="firstName" id="firstName" placeholder="First Name" required>

                    <input class="form-control mb-1 text-center" type="text" name="lastName" id="lastName" placeholder="Surname" required>

                        <input type="number" class="form-control text-center salaryInput" placeholder="Salary" min="0" required>
                
                    <div class="btn-group">
                      <button class="btn btn-info" v-on:click="setSalary">Submit</button>
                      <button class="btn btn-danger">Reset</button>
                    </div>
                  </form>
                  </div>
                </figure>
              </div>
  </div>
</template>

<script>
  let userIncome = document.querySelector('.salaryInput');

export default {
  name: 'Home',

  methods: {
    setSalary(){
      let userIncome=[{
        name: 'Total Salary',
        amount: document.querySelector('.salaryInput').value
      }]
      localStorage.setItem('userSalary',JSON.stringify(document.querySelector('.salaryInput').value))
      localStorage.setItem('userIncome',JSON.stringify(userIncome))
      this.$router.push('budget')

 }
}
}
</script>

<style scoped>
.container-fluid{
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  height: 85vh;
}
.flip-card {
    width: 50%;
    min-height: 50%;
    max-width: 30em;
    max-height: 30em;
    border-radius: 1.5em;
    
  }
  .flip-card .flip-card-inner .flip-card-front,
  .flip-card .flip-card-inner .flip-card-back{
    border-radius: 1.5em;
    
  }

.flip-card-front img{
    object-fit: cover;
    object-position: center;
    width: 100%;
    height: 100%;
}

  .flip-card-inner {
    position: relative;
    width: 100%;
    height: 100%;
    text-align: center;
    transition: all 0.5s ease-in-out;
    transform-style: preserve-3d;
  }
  
  .flip-card:hover .flip-card-inner {
    transform: rotateY(180deg);
  }
  
  .flip-card-front, .flip-card-back {
    position: absolute;
    width: 100%;
    height: 100%;
    backface-visibility: hidden;
  }
  
  .flip-card-front {
    color: black;
    display: flex;
    flex-flow: column nowrap;
    justify-content: center;
    align-items: center;
    background-color: rgba(255, 217, 0, 0.378);

  }
  
  .flip-card-back {
    padding: 0.5em;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: var(--darkCOLOR);
    color: var(--highlightCOLOR);
    transform: rotateY(180deg);
    background-color: rgba(222, 12, 12, 0.378);

  }

</style>
