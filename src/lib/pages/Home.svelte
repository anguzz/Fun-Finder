<script lang="ts">
  import Anchor from "$lib/components/Anchor.svelte";

 
</script>


<section>
  <Anchor id="home" />
<div
  class="flex flex-col items-center justify-center bg-center bg-no-repeat bg-cover page lg:bg-fixed bg-neutral-600 bg-blend-soft-light dark:bg-blend-soft-light dark:bg-neutral-700"
  id="bg"
>
<link href='https://fonts.googleapis.com/css?family=Yellowtail:400' rel='stylesheet' type='text/css'>

<h1 class="neonText">
  Fun <br> Finder
</h1>

</div>
</section>








<style>
  @import url('https://fonts.googleapis.com/css?family=Codystar:300&display=swap');
  #bg {
    width: 100%;
  height: 100vh;
  color: #fff;
  background-image: url("/src/bricks.jpg");
	background-size: 120% 120%; 
  position: relative;

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
  .neonText {
	 color: #1d448b;
	 text-shadow: 0 0 7px #3670c7#3670c7, 0 0 21px #3670c7, 0 0 42px #5271ff, 0 0 82px #5271ff, 0 0 92px #5271ff, 0 0 102px #5271ff, 0 0 151px #5271ff;
   font-size: 18px;
	 font-family: "Yellowtail", sans-serif;
   font-size: calc(3.5rem + 6vw);
}
 
h1 {
    font-size: 80px;
    color: #fff;
    text-align: center;
    text-shadow: 0 0 5px #fff, 0 0 10px #fff, 0 0 15px #0073e6, 0 0 20px #0073e6, 0 0 25px #0073e6, 0 0 30px #0073e6, 0 0 35px #0073e6;
}

</style>