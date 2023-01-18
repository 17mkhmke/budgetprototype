<template>
  <div class="container-fluid">
    <h1 class="display-5">Big Budget Corporation &copy;</h1>
    <div class="flip-card">
                <figure class="flip-card-inner">
                  <div class="flip-card-front">
                    <h2 class="lead">Hello</h2>
                  </div>
                  <div class="flip-card-back">
                    <p>Sign Up</p>
                  </div>
                </figure>
              </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container-fluid{
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  height: 85vh;
}
.flip-card {
    background-color: rgba(255, 217, 0, 0.378);
    width: 50%;
    min-height: 50%;
    max-width: 30em;
    max-height: 30em;
    border-radius: 1.5em;
    
  }
  .flip-card .flip-card-inner .flip-card-front img,
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
  }
  
  .flip-card-back {
    padding: 0.5em;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: var(--darkCOLOR);
    color: var(--highlightCOLOR);
    transform: rotateY(180deg);
  }

</style>
