<!-- Here we're manipulating the inner settings of the component -->
<svelte:options immutable={true} />

<script>
	export /**
* @type {{ name: any; }}
*/
	 let item
	$: console.log(item)
</script>

<li>
	{item.name}
</li>