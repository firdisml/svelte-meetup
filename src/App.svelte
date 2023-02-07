<script>
	import Header from "./ui/Header.svelte";
	import ItemGrid from "./meetups/ItemGrid.svelte";
	import Input from "./ui/Input.svelte";
	import Button from "./ui/Button.svelte";

	let title ='';
	let subtitle ='';
	let description = '';
	let image = '';
	let address = '';
	let email = '';

	let meetups = [
		{
			id: 'm1',
			title: 'Coding Bootcamp',
			subtitle: 'Learn to code in 2 hours',
			description: 'Relive the memory of last nights awards with our 65th',
			image: 'https://images.pexels.com/photos/15086603/pexels-photo-15086603.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1',
			address: 'Kuala Lumpur',
			email: 'test@gmail.com'
		},
		{
			id: 'm2',
			title: 'Coding Bootcamp',
			subtitle: 'Learn to code in 2 hours',
			description: 'Relive the memory of last nights awards with our 65th',
			image: 'https://images.pexels.com/photos/15086603/pexels-photo-15086603.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1',
			address: 'Kuala Lumpur',
			email: 'test@gmail.com'
		}
	]

	function add_meetup() {

		const new_meetup = {
			id: Math.random().toString(),
			title,
			subtitle,
			description,
			image,
			address,
			email,
		}

		meetups = [new_meetup, ...meetups]

	}

</script>

<style>
	main {
		margin-top: 5rem;
		padding-bottom: 1rem;
	}
	form {
		width: 30rem;
		max-width: 90%;
		margin: auto;
	}
</style>

<Header/>
<main>
	<form on:submit|preventDefault={add_meetup}>
		<Input id="title" control_type="input" label ="Title" value={title} on:input={(event) => (title = event.target.value)} />
		<Input id="subtitle" control_type="input" label ="Subtitle" value={subtitle} on:input={(event) => (subtitle = event.target.value)} />
		<Input id="description" control_type="textarea" rows={5} label ="Description" value={description} on:input={(event) => (description = event.target.value)} />
		<Input id="image" control_type="input" label ="Image" value={image} on:input={(event) => (image = event.target.value)} />
		<Input id="address" control_type="input" label ="Address" value={address} on:input={(event) => (address = event.target.value)} />
		<Input id="email" control_type="input" label ="Email" value={email} on:input={(event) => (email = event.target.value)} />
		<Button type="submit" caption="Save"/>
	</form>
<ItemGrid meetups={meetups}/>
</main>