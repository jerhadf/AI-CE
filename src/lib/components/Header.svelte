<script lang="ts">
	import { page } from '$app/stores';
	import ClearHistory from '$lib/components/ClearHistory.svelte';
	import Sidebar from '$lib/components/Sidebar.svelte';
	import SidebarFooter from '$lib/components/SidebarFooter.svelte';
	import SidebarList from '$lib/components/SidebarList.svelte';
	import ThemeToggle from '$lib/components/ThemeToggle.svelte';
	// import UserMenu from '$lib/components/UserMenu.svelte';
	import { buttonVariants } from '$lib/components/ui/button';
	import { IconGitHub, IconSeparator } from '$lib/components/ui/icons';
	import type { Chat } from '$lib/types';
	import { cn } from '$lib/utils';
	import { IconAICE } from '$lib/components/ui/icons';
	export let chats: Chat[];
</script>

<header
class="sticky top-0 z-50 flex h-16 w-full shrink-0 items-center justify-between border-b bg-gradient-to-b from-background/10 via-background/50 to-background/80 px-4 backdrop-blur-xl"
>
	<div class="flex items-center">
		<IconAICE class="h-6 w-6" />
	</div>
	<div class="flex items-center justify-end space-x-2">
		<a
			target="_blank"
			href="https://github.com/jerhadf/AI-CE"
			rel="noopener noreferrer"
			class={cn(buttonVariants({ variant: 'outline' }))}
		>
			<IconGitHub />
			<span class="ml-2 hidden md:flex">GitHub</span>
		</a>
	</div>
</header>