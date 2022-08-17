<script lang="ts">
  import Page from "$lib/components/Page.svelte";
  import { primaryBackground } from "$lib/utils/constants";
 
  export let backgroundClass = primaryBackground;

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

<Page id="content" title=" " {backgroundClass}>
	<div class="page-wrapper">
		
		<div class="container">
			<div class="row">
			  <div class="col-md-12 text-center">
				<h3 class="animate-charcter"> Fun Finder</h3>
			  </div>
			</div>
		  </div>
	
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
			<span style="--i:1">L</span>
			<span style="--i:2">o</span>
			<span style="--i:3">a</span>
			<span style="--i:4">d</span>
			<span style="--i:5">i</span>
			<span style="--i:6">n</span>
			<span style="--i:7">g</span>
		   </div>
		
		  {/if}
		</div>
	  </div>
	  
</Page>


<style>
   h1 {
    font-size: clamp(2rem, 5vw, 6rem);
    color: #6ccee7;
  }
  .page-wrapper {
    text-align: center;
	color: #1F2937;
	background-color: #1F2937;
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
 body {
	 min-height: 100vh;
	 font-family: canada-type-gibson, sans-serif;
	 font-weight: 300;
	 font-size: .8rem;
	 display: flex;
	 flex-direction: column;
	 justify-content: center;
	 overflow: hidden;
	 background-color: #eff8e2;
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
 @keyframes shadows {
	 0% {
		 text-shadow: none;
	}
	 10% {
		 text-shadow: 3px 3px 0 var(--color-secondary);
	}
	 20% {
		 text-shadow: 3px 3px 0 var(--color-secondary), 6px 6px 0 var(--color-tertiary);
	}
	 30% {
		 text-shadow: 3px 3px 0 var(--color-secondary), 6px 6px 0 var(--color-tertiary), 9px 9px var(--color-quaternary);
	}
	 40% {
		 text-shadow: 3px 3px 0 var(--color-secondary), 6px 6px 0 var(--color-tertiary), 9px 9px var(--color-quaternary), 12px 12px 0 var(--color-quinary);
	}
	 50% {
		 text-shadow: 3px 3px 0 var(--color-secondary), 6px 6px 0 var(--color-tertiary), 9px 9px var(--color-quaternary), 12px 12px 0 var(--color-quinary);
	}
	 60% {
		 text-shadow: 3px 3px 0 var(--color-secondary), 6px 6px 0 var(--color-tertiary), 9px 9px var(--color-quaternary), 12px 12px 0 var(--color-quinary);
	}
	 70% {
		 text-shadow: 3px 3px 0 var(--color-secondary), 6px 6px 0 var(--color-tertiary), 9px 9px var(--color-quaternary);
	}
	 80% {
		 text-shadow: 3px 3px 0 var(--color-secondary), 6px 6px 0 var(--color-tertiary);
	}
	 90% {
		 text-shadow: 3px 3px 0 var(--color-secondary);
	}
	 100% {
		 text-shadow: none;
	}
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
/**loading animation */

.waviy {
  position: relative;
  -webkit-box-reflect: below -20px linear-gradient(transparent, rgba(0,0,0,.2));
  font-size: 60px;
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
.animate-charcter
{
	
   text-transform: uppercase;
  background-image: linear-gradient(
    -225deg,
    #319be2 0%,
    #22c1dd 29%,
    #132bff 67%,
    #91def1 100%
  );
  background-size: auto auto;
  background-clip: border-box;
  background-size: 200% auto;

  background-clip: text;

  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: textclip 2s linear infinite;
  display: inline-block;
  font-size: calc(1.5rem + 3vw);
}

@keyframes textclip {
  to {
    background-position: 200% center;
  }
}
</style>

