<script lang="ts">
	import { copyToClipboard } from '$lib/utils';
	import { Label } from '$lib/components/ui/label';
	import { Input } from '$lib/components/ui/input';
	import { Button } from '$lib/components/ui/button';
	import Separator from '$lib/components/ui/separator/separator.svelte';

	let phoneScreen = $state('');
	let firstImage = $state('');
	let secondImage = $state('');
	let thirdImage = $state('');
	let fourthImage = $state('');

	const htmlValue = $derived(`
  <div class="flex flex-col lg:flex-row gap-8 items-center my-14">
 <div class="relative shrink-0 mx-auto flex justify-center h-[600px] w-[290px] border-4 border-black rounded-2xl"
    style="box-shadow: 10px 10px 5px 12px rgb(209, 218, 218)">
    <span class="absolute top-2 left-1/2 -translate-x-1/2 border z-20 border-black bg-black w-16 h-4 mt-2 rounded-full"></span>

    <span class="absolute -right-1.5 top-20 border-2 border-black h-10 rounded-md"></span>

    <span class="absolute -left-1.5 top-16 border-2 border-black h-6 rounded-md"></span>
    <span class="absolute -left-1.5 top-32 border-2 border-black h-12 rounded-md"></span>
    <span class="absolute -left-1.5 top-48 border-2 border-black h-12 rounded-md"></span>
      <div class="w-full h-full bg-black/[0.7]">
        <video class="w-full object-cover object-center rounded-xl -z-10 h-full m-0" src="${phoneScreen}" alt="Automated video ad featuring stylish skirt" autoplay muted loop playsinline></video>
      </div>
  </div>

  <div class="grid sm:grid-cols-2 grid-cols-1 gap-4 items-center">
    <div>
      <img src="${firstImage}" class="w-full h-auto rounded-lg" alt="Company looking for a new team member" />
    </div>

    <div>
      <img src="${secondImage}" class="w-full h-auto rounded-lg" alt="Person looking for a new job" />
    </div>

    <div>
      <img src="${thirdImage}" class="w-full h-auto rounded-lg" alt="Recruiter calls to screen a candidate" />
    </div>

    <div>
      <img src="${fourthImage}" class="w-full h-auto rounded-lg" alt="Person got a job offer" />
    </div>
  </div>
</div>`);
</script>

<div class="flex w-full flex-col gap-4 mb-5">
	<h2 class="text-2xl font-semibold text-center text-gray-900">Modify data for this Snippet</h2>
	<div class="flex flex-wrap gap-3 items-center justify-between">
		<Label for="image">Screen</Label>
		<Input
			class="max-w-3xl w-full"
			id="image"
			bind:value={phoneScreen}
			placeholder="Enter screen video url"
		/>
	</div>
	<div class="flex flex-wrap gap-3 items-center justify-between">
		<Label for="author">First image</Label>
		<Input
			class="max-w-3xl w-full"
			id="author"
			bind:value={firstImage}
			placeholder="Enter first image url"
		/>
	</div>
	<div class="flex flex-wrap gap-3 items-center justify-between">
		<Label for="author">Second image</Label>
		<Input
			class="max-w-3xl w-full"
			id="author"
			bind:value={secondImage}
			placeholder="Enter second image url"
		/>
	</div>
	<div class="flex flex-wrap gap-3 items-center justify-between">
		<Label for="author">Third image</Label>
		<Input
			class="max-w-3xl w-full"
			id="author"
			bind:value={thirdImage}
			placeholder="Enter third image url"
		/>
	</div>
	<div class="flex flex-wrap gap-3 items-center justify-between">
		<Label for="author">Fourth image</Label>
		<Input
			class="max-w-3xl w-full"
			id="author"
			bind:value={fourthImage}
			placeholder="Enter fourth image url"
		/>
	</div>

	<Button onclick={() => copyToClipboard(htmlValue)} class="mx-auto" type="submit"
		>Copy to clipboard</Button
	>
</div>

<Separator class="w-full mb-5" />

<h2 class="text-lg text-center font-bold">How it will look like</h2>

<div class="max-w-4xl">
  {@html htmlValue}
</div>
