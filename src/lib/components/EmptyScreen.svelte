<script lang="ts">
	import ExternalLink from '$lib/components/ExternalLink.svelte';
	import { Button } from '$lib/components/ui/button';
	import { IconArrowRight } from '$lib/components/ui/icons';
	import type { UseChatHelpers } from 'ai/svelte/dist';

	export let input: UseChatHelpers['input'];

	const exampleMessages = [
		{
			heading: 'Explain the theory',
			message: `What is a metalinguistic negotiation?`
		},
		{
			heading: 'Identify defects',
			message: 'Perform analysis on the concept <freedom> to identify defects: \n'
		},
		{
			heading: 'Engineer a concept',
			message: `Apply the full conceptual engineering process to <mental illness>: \n`
		}
	];
</script>

<div class="mx-auto max-w-2xl px-4">
	<div class="rounded-lg border bg-background p-8">
		<h1 class="mb-2 text-lg font-semibold">Welcome to the AI conceptual engineer!</h1>
		<p class="mb-2 leading-normal text-muted-foreground">
			This is an open source AI tool to aid with conceptual engineering, built with
			<ExternalLink href="https://kit.svelte.dev">SvelteKit</ExternalLink>,
			<ExternalLink href="https://vercel.com/storage/kv">Vercel KV</ExternalLink> and
			<ExternalLink href="https://docs.smith.langchain.com/overview"> LangChain </ExternalLink>
		</p>
		<p class="leading-normal text-muted-foreground">
			You can start a conversation here or try the following examples:
		</p>
		<div class="mt-4 flex flex-col items-start space-y-2">
			{#each exampleMessages as message}
				<Button
					variant="link"
					class="h-auto p-0 text-base"
					on:click={() => ($input = message.message)}
				>
					<IconArrowRight class="mr-2 text-muted-foreground" />
					{message.heading}
				</Button>
			{/each}
		</div>
	</div>
</div>
