<script>
	import EventTable from "../components/EventTable.svelte";
  import HomePage from "../components/HomePage.svelte";
  import MobileScreen from "../components/MobileScreen.svelte";
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
<div class="desktopScreen md:block hidden">
	<HomePage/>
</div>
<div class="desktopScreen md:hidden">
	<MobileScreen/>
	
</div>
</section>

