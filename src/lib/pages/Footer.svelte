<script lang="ts">
  import Link from "$lib/components/Link.svelte";
  import Footer from "$lib/components/Footer.svelte";
  import Text from "$lib/components/Text.svelte";
  import { primaryBackground } from "$lib/utils/constants";

  export let backgroundClass = primaryBackground;
</script>

<Footer id="Footer" title=" " {backgroundClass}>

<footer id="theme" class='bottom-0 left-0 flex flex-col w-full gap-8 px-8 py-16 md:gap-12'>
  
  <div class='w-full h-px m-auto bg-gradient-to-r from-transparent via-blue-400 to-transparent'></div>
  <div class='flex flex-col items-center gap-8 md:justify-between md:flex-row'>
    <div class='flex flex-col gap-2'>
      <footer>
          <div class="footer-content">
              <h3>Angel Santoyo</h3>
              <p>Feel free to check out my other projects or contact me below</p>
          </div>
  <div class='w-full h-px m-auto bg-gradient-to-r from-transparent via-gray-700 to-transparent'></div>
  <div class='flex flex-col items-center gap-6 md:flex-row md:justify-between'>
    <div class=copyright>
      &#169; 2022
    </div>
    <div class='flex gap-4 p-2 rounded-md social-wrapper'>
      <a href="mailto:santoyox714@gmail.com">         <img src = 'gmail.png'   width="65px"  alt=git/> </a>            
      <a href="https://github.com/Angus-1">            <img src = 'github.png'  width="65px" alt=gmail/> </a>          
      <a href="https://www.linkedin.com/in/asantoyo/"> <img src = 'linkedin.png'width="60px" alt=linkedin/> </a>
    </div>
  </div>
</footer>
  
 
</Footer>


<style>
@import url("https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,400;0,500;0,700;0,900;1,300&display=swap");
:root {
--gray-50: #f9fafb;
--gray-100: #f3f4f6;
--gray-300: #d1d5db;
--gray-400: #93a3af;
--gray-500: #6b7280;
--gray-600: #4b5563;
--gray-700: #374151;
--gray-800: #1f2937;
--gray-900: #111827;
}
.footer-content h3{
  font-size: 2.1rem;
  font-weight: 500;
  text-transform: capitalize;
  line-height: 3rem;
}
.footer-content p{
  max-width: 500px;
  margin: 10px auto;
  color: rgb(131, 176, 204);
  
} 
#theme {
--primary: #1f2937;
--comp-primary: #f3f4f6;
--white: white;
--gray-200: #374151;
--black: black;
}
footer {
background-color: var(--primary);
color: var(--white);
box-shadow: 1px -5px var(--blur) rgba(0, 0, 0, 0.3);
}
* {
transition: all 0.3s ease;
}
.divider {
filter: blur(1px);
}
input,
textarea {
background-color: var(--comp-primary);
color: var(--black);
}
.nav-modal {
background-color: var(--primary);
}
button {
background-color: var(--comp-primary);
color: var(--primary);
}
.social-wrapper {
background-color: #111827;
border: 1px solid var(--comp-primary);
}
.copyright{
 font-weight:bold;
 font-size: large;
}
</style>