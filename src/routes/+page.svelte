<script lang="ts">
	import { supabase } from '$lib/supabaseClient';

	let sessions = [];

	const fetchSessions = async () => {
		const { data, error } = await supabase.from('JamSession').select('*');
		if (error) {
			console.error('Error fetching sessions:', error);
		} else {
			sessions = data;
		}
	};

	fetchSessions();
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>

<h2>Jam Sessions</h2>
<ul>
	{#each sessions as session}
		<li>{session.title} - {session.date}</li>
	{/each}
</ul>
