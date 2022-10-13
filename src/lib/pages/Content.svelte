<script lang="ts">
	import Anchor from "$lib/components/Anchor.svelte";

 
  

  import {OPTIONS} from "$lib/pages/options.js";
  let selectedOption: { options: string|any[]; };
  let selectedRandomOption: string;
  let loading = false;

  const handleRandomize = () => {
    loading = true;
    setTimeout(() => {
      loading = false;
      if (selectedOption) {
        selectedRandomOption =
          selectedOption.options[
            Math.floor(Math.random() * selectedOption.options.length)
          ];
      }
    }, 1000);
  };
  </script>
  
  
  <section>
	<Anchor id="content" />
  <div
	class="flex flex-col items-center justify-center bg-center bg-no-repeat bg-cover page lg:bg-fixed bg-neutral-600 bg-blend-soft-light dark:bg-blend-soft-light dark:bg-neutral-700"
	id="bg"
  >


		<div class="page-wrapper">

			<h1 class="neonText">
				-Go have some fun-
			  </h1>
			  
			  <div id="mcontainer">
				<div id="monitor">
				  <div id="monitorscreen">

					<select
					bind:value={selectedOption}
					on:change={() => {
					  loading = false;
					  selectedRandomOption = "";
					}}	>
					<option value="">------</option>
					{#each OPTIONS as randomOption}
					  <option value={randomOption}>
								  <h2 class="text_shadows"> {randomOption.displayText}</h2>
					  </option>
					{/each}
				  </select>
			  
				  <button on:click={handleRandomize} disabled={!selectedOption || loading}>
					Randomize!
				  </button>
				
				  <div class="selected-option">
					{#if selectedRandomOption && !loading}
					<div class="content">
					  <h2 class="text_shadows">	{selectedRandomOption}</h2>
					</div>	
					{/if}
					{#if loading === true}
					<div class="waviy">
					  <span style="--i:1">.</span>
					  <span style="--i:2">.</span>
					  <span style="--i:3">.</span>
					  <span style="--i:4">.</span>
					  <span style="--i:5">.</span>
					  <span style="--i:6">.</span>
					  <span style="--i:7">.</span>
					 </div>
				  
					{/if}


				  </div>
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
	background-image: url("/src/bricks.jpg");
	background-size: 120% 120%;
	position: relative;
	
	}
	* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
  }
  
  
  
  
   
	/* --------------------------  title css--------------------------*/
	@import url('https://fonts.googleapis.com/css?family=Codystar:300&display=swap');
  
  body {
	 display: flex;
	 justify-content: center;
	 align-items: center;
	 font-family: 'Codystar';
  }
  
  


  /*----------------------------------------------- */
  
  /*---------- */
  .page-wrapper {
	
    text-align: center;
	color: #1F2937;
	
	border-radius:10px;
	
	
  }
  button {
    cursor: pointer;
    margin-left: 1rem;
    padding: 0.5rem 1rem;
    color: #1F2937;
    border-color: #558492;
    border-radius: 5px;
    font-weight: bold;
	background-color: #7ac2ec;
  }
  button:disabled {
    pointer-events: none;
	background-color: #2e70d3;
  }
  button:active {
    transform: scale(0.98);
	color:#08415c;
	background-color: #7ac8ec;
  }
  
  button:hover {
    background-color: #54a0df;
    border-color: #074183;
  }
  .selected-option {
    margin-top: 1.5rem;
    font-size: 1.5rem;
    color: #85f0b5;
    font-weight: 600;
	
  }

 
/* ---------------------------- chosen place animation css-----------------------------  */
 :root {
	 --color-primary: #a2dcf6;
	 --color-secondary: #90f1f4;
	 --color-tertiary: #3d73b1;
	 --color-quaternary: #6aa4f0;
	 --color-quinary: #0c2363;
}

 .content {
	 display: flex;
	 align-content: center;
	 justify-content: center;
}
.text_shadows {
  text-shadow: 3px 3px 0 var(--color-secondary), 6px 6px 0 var(--color-tertiary),
    9px 9px var(--color-quaternary), 12px 12px 0 var(--color-quinary);
  font-family: bungee, sans-serif;
  font-weight: 200;
  text-transform: uppercase;
  font-size: calc(1.5rem + 3vw);
  text-align: center;
  margin: 0;
  color: var(--color-primary);
  
  animation: shadows 2.00s ease-in infinite, move 3.2s ease-in infinite;

  letter-spacing: 0.4rem;
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
 
 @keyframes move {
	 0% {
		 transform: translate(0px, 0px);
	}
	 40% {
		 transform: translate(-12px, -12px);
	}
	 50% {
		 transform: translate(-12px, -12px);
	}
	 60% {
		 transform: translate(-12px, -12px);
	}
	 100% {
		 transform: translate(0px, 0px);
	}
}
/* --------------------------------------------------loading animation --------------------------------------------------*/

.waviy {
  position: relative;
  -webkit-box-reflect: below -20px linear-gradient(transparent, rgba(0,0,0,.2));
  font-size: calc(1.5rem + 3vw);
}
.waviy span {
  position: relative;
  display: inline-block;
  color: rgb(131, 196, 250);
  text-transform: uppercase;
  animation: waviy 1s infinite;
  animation-delay: calc(.1s * var(--i));
  
}
@keyframes waviy {
  0%,40%,100% {
    transform: translateY(0)
  }
  20% {
    transform: translateY(-20px)
  }
}
/**============================title css ============================================*/

.neonText {
	color: #60b8e0;
	 text-shadow: 0 0 7px #3670c7#3670c7, 0 0 21px #3670c7, 0 0 42px #5271ff, 0 0 82px #5271ff, 0 0 92px #5271ff, 0 0 102px #5271ff, 0 0 151px #5271ff;
   font-size: 18px;
	 font-family: "Yellowtail", sans-serif;
   font-size: calc(3.5rem + 3vw);
}
 
h1 {
    font-size: 80px;
    color: #fff;
    text-align: center;
    text-shadow: 0 0 5px #fff, 0 0 10px #fff, 0 0 15px #0073e6, 0 0 20px #0073e6, 0 0 25px #0073e6, 0 0 30px #0073e6, 0 0 35px #0073e6;
}




/**============================monitor css ============================================*/



#monitor {
	background: #000; 
	position: relative;
	border-top: 3px solid #888; 
	margin: 5%;
	padding: 2% 2% 4% 2%; 
	border-radius: 10px; 
	border-bottom-left-radius: 50% 2%; 
	border-bottom-right-radius: 50% 2%; 
	transition: margin-right 1s;
}

#monitor:after {
	content: '';
	display: block;
	position: absolute;
	bottom: 3%;
	left: 36%;
	height: .5%; 
	width: 28%;
	background: #ddd; 
	border-radius: 50%; 
	box-shadow: 0 0 3px 0 white; 
}

#monitorscreen {
	position: relative;
  background-color: rgb(60, 61, 60);
	background-size: cover; 
	background-position: top center;
	height: 0; 
	padding-bottom: 56.25%; 
	position: relative;
	overflow: hidden;
}


@media all and (min-width: 960px) {
	#monitor {
		-webkit-animation: tvflicker .2s infinite alternate; 
		-moz-animation:    tvflicker .5s infinite alternate; 
		-o-animation:      tvflicker .5s infinite alternate; 
		animation:         tvflicker .5s infinite alternate; 
	}

	@-webkit-keyframes tvflicker {
	  0%   { box-shadow: 0 0 100px 0 rgba(200,235,255,0.4); }
	  100% { box-shadow: 0 0 95px 0 rgba(200,230,255,0.45); }
	}
	@-moz-keyframes tvflicker {
	  0%   { box-shadow: 0 0 100px 0 rgba(225,235,255,0.4); }
	  100% { box-shadow: 0 0 60px 0 rgba(200,220,255,0.6); }
	}
	@-o-keyframes tvflicker {
	  0%   { box-shadow: 0 0 100px 0 rgba(225,235,255,0.4); }
	  100% { box-shadow: 0 0 60px 0 rgba(200,220,255,0.6); }
	}
	@keyframes tvflicker {
	  0%   { box-shadow: 0 0 100px 0 rgba(225,235,255,0.4); }
	  100% { box-shadow: 0 0 60px 0 rgba(200,220,255,0.6); }
	}
}
  </style>