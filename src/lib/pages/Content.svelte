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
		<h1>Fun Finder</h1>
		<select
		  bind:value={selectedOption}
		  on:change={() => {
			loading = false;
			selectedRandomOption = "";
		  }}	>
		  <option value="">-- Choose an Option --</option>
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
			<p>Randomizing...</p>
		  {/if}
		</div>
	  </div>
	  
</Page>


<style>
   h1 {
    font-size: clamp(2rem, 5vw, 6rem);
    color: #6ce7c9;
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
    border-color: #709255;
    border-radius: 5px;
    font-weight: bold;
	background-color: #7aecca;
  }
  button:disabled {
    pointer-events: none;
	background-color: #7abeec;
  }
  button:active {
    transform: scale(0.98);
	color:#08415c;
	background-color: #7ac8ec;
  }
  
  button:hover {
    background-color: #7ac8ec;
    border-color: #8b7aec;
  }
  .selected-option {
    margin-top: 1.5rem;
    font-size: 1.5rem;
    color: #85f0b5;
    font-weight: 600;
	
  }

 
/* ---------------------------- letter animation css-----------------------------  */
 :root {
	 --color-primary: #f6aca2;
	 --color-secondary: #f49b90;
	 --color-tertiary: #f28b7d;
	 --color-quaternary: #f07a6a;
	 --color-quinary: #ee6352;
	/* --color-primary: #5192ED;
	 --color-secondary: #69A1F0;
	 --color-tertiary: #7EAEF2;
	 --color-quaternary: #90BAF5;
	 --color-quinary: #A2C4F5;
	 */
}
 body {
	 min-height: 100vh;
	 font-family: canada-type-gibson, sans-serif;
	 font-weight: 300;
	 font-size: 1.25rem;
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
	 text-shadow: 3px 3px 0 var(--color-secondary), 6px 6px 0 var(--color-tertiary), 9px 9px var(--color-quaternary), 12px 12px 0 var(--color-quinary);
	 font-family: bungee, sans-serif;
	 font-weight: 400;
	 text-transform: uppercase;
	 font-size: calc(2rem + 5vw);
	 text-align: center;
	 margin: 0;
	 color: var(--color-primary);
	 animation: shadows 1.2s ease-in infinite, move 1.2s ease-in infinite;
	 letter-spacing: 0.4rem;
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
</style>

