<script lang="ts">
  import Anchor from "$lib/components/Anchor.svelte";

 

</script>


<section>
  <Anchor id="home" />
<div
  class="flex flex-col items-center justify-center bg-center bg-no-repeat bg-cover page lg:bg-fixed bg-neutral-600 bg-blend-soft-light dark:bg-blend-soft-light dark:bg-neutral-700"
  id="bg"
>
<div class="container">
  <div class="row">
     <div class="neons col-12">
        <h1><em>Fun Finder</em></h1>
     </div>
  </div>
</div>

</div>
</section>

<style>
  #bg {
    width: 100%;
  height: 100vh;
  color: #fff;
  background-image: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
  background-size: 400% 400%;
  position: relative;
  animation: change 10s ease-in-out infinite;
  }
  * {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}



@keyframes change {
  0% {
    background-position: 0 50%;
  }
  
  50% {
    background-position: 100% 50%;
  }
  
  100% {
    background-position: 0 50%;
  }
}
 
  /* --------------------------  title css--------------------------*/
  @import url('https://fonts.googleapis.com/css?family=Codystar:300&display=swap');

body {
   display: flex;
   justify-content: center;
   align-items: center;
   font-family: 'Codystar';
}

.neons {
   text-align: center;
}

.neons h1 {
  font-size: calc(3.5rem + 4vw);
  text-align: center;
   font-weight: bold;
  -webkit-animation: glow 2s ease-in-out infinite alternate;
  -moz-animation: glow 2s ease-in-out infinite alternate;
  animation: glow 2s ease-in-out infinite alternate;
}

@-webkit-keyframes glow {
     from {
      color: #fff;
    text-shadow: 0 0 10px #00fff2, 0 0 20px #00fff2, 0 0 30px #00fff2, 0 0 40px #00fff2, 0 0 50px #00fff2, 0 0 60px #00fff2, 0 0 70px #00fff2, 0 0 90px #00fff2;
  }
  
  to {
     color: gray;
    text-shadow: 0 0 20px #00fff2, 0 0 30px #00fff2, 0 0 40px #00fff2, 0 0 50px #00fff2, 0 0 60px #00fff2, 0 0 70px #00fff2, 0 0 80px #00fff2, 0 1 90px #00fff2;
  }
}
</style>