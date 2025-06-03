<script lang="ts">
	import * as Tabs from '$lib/components/ui/tabs';
	import Quates from '$lib/app//Quates.svelte';
	import TwoPhoneScreens from '$lib/app/TwoPhoneScreens.svelte';
	import PhoneWithGrid from '$lib/app/PhoneWithGrid.svelte';
	import CompanyQuotes from '$lib/app/CompanyQuotes.svelte';
</script>

<svelte:head>
	<title>Copy HTML snippets</title>
</svelte:head>
<main class="flex flex-col items-center gap-10">
	<h1 class="text-center text-2xl">Choose your snippet</h1>
	<Tabs.Root value="quates" class="mx-auto overflow-x-hidden w-full px-10">
		<Tabs.List class="mx-auto">
			<Tabs.Trigger value="quates">Quote</Tabs.Trigger>
			<Tabs.Trigger value="twoPhoneScreens">Two phone sreens</Tabs.Trigger>
			<Tabs.Trigger value="phoneWithGrid">Phone with Grid</Tabs.Trigger>
			<Tabs.Trigger value="companyQuotes">Company Quotes</Tabs.Trigger>
		</Tabs.List>
		<Tabs.Content class="overflow-x-hidden" value="quates">
			<Quates />
		</Tabs.Content>
		<Tabs.Content value="twoPhoneScreens">
			<TwoPhoneScreens />
		</Tabs.Content>
		<Tabs.Content value="phoneWithGrid">
			<PhoneWithGrid />
		</Tabs.Content>
		<Tabs.Content value="companyQuotes">
			<CompanyQuotes />
		</Tabs.Content>
	</Tabs.Root>
</main>
