<script lang="ts">
  import Anchor from "$lib/components/Anchor.svelte";

 
  let color = "text-grey-200";
  let hover = "sm:hover:text-primary-500";
 
</script>

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



















<style>
  #bg {
    /* The image used background-image: url("/assets/images/background1.jpg"); */
    background-image: linear-gradient(217deg, rgba(0, 248, 165, 0.8), rgba(255,0,0,0) 70.71%),
      linear-gradient(127deg, rgba(0, 4, 255, 0.8), rgba(0,255,0,0) 70.71%),
      linear-gradient(336deg, rgba(248, 248, 248, 0.8), rgba(0,0,255,0) 70.71%);
    
  }

 
  /*  */
  @import url('https://fonts.googleapis.com/css?family=Codystar:300&display=swap');

body {
   display: flex;
   justify-content: center;
   align-items: center;
   font-family: 'Codystar';
   background: black;
   background-image: url('data:image/svg+xml,%3Csvg width="42" height="44" viewBox="0 0 42 44" xmlns="http://www.w3.org/2000/svg"%3E%3Cg id="Page-1" fill="none" fill-rule="evenodd"%3E%3Cg id="brick-wall" fill="%239C92AC" fill-opacity="0.4"%3E%3Cpath d="M0 0h42v44H0V0zm1 1h40v20H1V1zM0 23h20v20H0V23zm22 0h20v20H22V23z"/%3E%3C/g%3E%3C/g%3E%3C/svg%3E');
}

.neons {
   margin-top: 10rem;
   text-align: center;
}

.neons h1 {
  font-size: 9rem;
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