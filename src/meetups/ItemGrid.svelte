<script>
    import Item from "./Item.svelte";

    export let meetups;


</script>

<style>
    section {
  width: 100%;
  display: grid;
  grid-template-columns: 1fr;
  grid-gap: 1rem;
}

@media (min-width: 768px) {
  section {
    grid-template-columns: repeat(2, 1fr);
  }
}

</style>

<section id="meetups">
	{#each meetups as meetup (meetup.id)}
		<Item title={meetup.title} subtitle={meetup.subtitle} description={meetup.description} image={meetup.image} email={meetup.email} address={meetup.address}/>
	{/each}
</section>
