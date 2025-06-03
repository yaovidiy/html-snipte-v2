<script lang="ts">
	import { copyToClipboard } from '$lib/utils';
	import { Label } from '$lib/components/ui/label';
	import { Input } from '$lib/components/ui/input';
	import { Button } from '$lib/components/ui/button';
	import { Separator } from '$lib/components/ui/separator';

	let firstPhoneScreen = $state('');
	let secondPhoneScreen = $state('');
	let htmlValue = $derived(`
  <div class="flex flex-col mt-14 md:flex-row gap-10">
 <div class="relative mx-auto flex justify-center h-[520px] w-[290px] border-4 border-black rounded-2xl"
    style="box-shadow: 10px 10px 5px 12px rgb(209, 218, 218)">
    <span class="absolute top-2 left-1/2 -translate-x-1/2 border z-20 border-black bg-black w-16 h-4 mt-2 rounded-full"></span>

    <span class="absolute -right-1.5 top-20 border-2 border-black h-10 rounded-md"></span>

    <span class="absolute -left-1.5 top-16 border-2 border-black h-6 rounded-md"></span>
    <span class="absolute -left-1.5 top-32 border-2 border-black h-12 rounded-md"></span>
    <span class="absolute -left-1.5 top-48 border-2 border-black h-12 rounded-md"></span>
      <div class="w-full h-full bg-black/[0.7]">
        <video class="w-full object-cover object-center rounded-xl -z-10 h-full m-0" src="${firstPhoneScreen}" alt="Automated video ad featuring stylish skirt" autoplay muted loop playsinline></video>
      </div>
  </div>
  <div class="relative mx-auto flex justify-center h-[520px] w-[290px] border-4 border-black rounded-2xl"
    style="box-shadow: 10px 10px 5px 12px rgb(209, 218, 218)">
    <span class="absolute top-2 left-1/2 -translate-x-1/2 border z-20 border-black bg-black w-16 h-4 mt-2 rounded-full"></span>

    <span class="absolute -right-1.5 top-20 border-2 border-black h-10 rounded-md"></span>

    <span class="absolute -left-1.5 top-16 border-2 border-black h-6 rounded-md"></span>
    <span class="absolute -left-1.5 top-32 border-2 border-black h-12 rounded-md"></span>
    <span class="absolute -left-1.5 top-48 border-2 border-black h-12 rounded-md"></span>
      <div class="w-full h-full bg-black/[0.7]">
        <video class="w-full object-cover rounded-xl -z-10 h-full m-0" src="${secondPhoneScreen}" alt="Automated video ad featuring stylish skirt" autoplay muted loop playsinline></video>
      </div>
  </div>
</div>`);
</script>

<div class="mb-5 flex w-full flex-col gap-4">
	<h2 class="text-center text-2xl font-semibold text-gray-900">Modify data for this Snippet</h2>
	<div class="flex flex-wrap items-center justify-between gap-3">
		<Label for="image">First screen video</Label>
		<Input
			class="w-full max-w-3xl"
			id="image"
			bind:value={firstPhoneScreen}
			placeholder="Enter first screen video url"
		/>
	</div>
	<div class="flex flex-wrap items-center justify-between gap-3">
		<Label for="author">Second screen image or video</Label>
		<Input
			class="w-full max-w-3xl"
			id="author"
			bind:value={secondPhoneScreen}
			placeholder="Enter second screen video url"
		/>
	</div>

	<Button onclick={() => copyToClipboard(htmlValue)} class="mx-auto" type="submit"
		>Copy to clipboard</Button
	>
</div>

<Separator class="mb-5 w-full" />

<h2 class="text-center text-lg font-bold">How it will look like</h2>

{@html htmlValue}
