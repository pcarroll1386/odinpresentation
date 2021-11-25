<script context="module">
	export const load = async ({ fetch, page: {params} }) => {
        const {slug} = params
		const res = await fetch(`/posts/${slug}.json`);
        console.log(res)
		if (res.ok) {
			const { post } = await res.json();
			return { props: { post } };
		}
	};
</script>

<script>
    export let post
</script>
<svelte:head>
    <title>Why Odin Sucks</title>
</svelte:head>

<pre>{JSON.stringify(post, null, 2)}</pre>