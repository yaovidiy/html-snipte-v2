<script lang="ts">
	import { Label } from '$lib/components/ui/label';
	import { Input } from '$lib/components/ui/input';
	import { Textarea } from '$lib/components/ui/textarea';
	import { Button } from '$lib/components/ui/button';
	import { Separator } from '$lib/components/ui/separator';
	import { copyToClipboard } from '$lib/utils';
	import { Slider } from '$lib/components/ui/slider';
	import * as Select from '$lib/components/ui/select';

	let quoteCompanyLogo = $state(
		'https://nx-website-assets.nexrender.com/Videohebel_2_184dc2c21e.png'
	);
	let quoteCompanyLogoHeight = $state(2);
	let quoteCompanyLogoHeightUnit = $state('rem'); // 'auto', '%', 'rem', 'px'
	let quoteCompanyLogoWidth = $state(2);
	let quoteCompanyLogoWidthUnit = $state('auto'); // 'auto', '%', 'rem', 'px'
	let quote = $state(
		'"Nexrender enables us to deliver highly personalized guest experiences effortlessly. Automating video production at scale has never been this efficient. I just love it!"'
	);
	let quoteAuthorImage = $state('https://nx-website-assets.nexrender.com/tk1_cc96af809e.jpg');
	let quoteAuthorImageHeight = $state(40);
	let quoteAuthorImageWidth = $state(40);
	let quoteAuthorImageHeightUnit = $state('px'); // 'auto', '%', 'rem', 'px'
	let quoteAuthorImageWidthUnit = $state('px'); // 'auto', '%', 'rem', 'px'
	let quoteAuthor = $state('Torben Karg');
	let quoteAuthorTextSize = $state(0);
	let quoteAuthorTextSizeUnit = $state('auto'); // 'auto', '%', 'rem', 'px'
	let quoteAuthorLineHeight = $state(0);
	let quoteAuthorTitle = $state('Founder, Videohebel');
	let quoteAuthorTitleTextSize = $state(0);
	let quoteAuthorTitleTextSizeUnit = $state('auto'); // 'auto', '%', 'rem', 'px'
	let quoteAuthorTitleLineHeight = $state(0);
	let quoteTextSize = $state(0);
	let quoteTextSizeUnit = $state('auto'); // 'auto', '%', 'rem', 'px'
	let quoteLineHeight = $state(0);
	let blockMargin = $state(0);
	let blockMarginUnit = $state('auto'); // 'auto', '%', 'rem', 'px'
	let sectionPaddingInline = $state(2);
	let sectionPaddingBlock = $state(2);
	let sectionPaddingInlineUnit = $state('auto'); // 'auto', '%', 'rem', 'px'
	let sectionPaddingBlockUnit = $state('auto'); // 'auto', '%', 'rem', 'px'
	let authorBlockGap = $state(3);
	let authorBlockGapUnit = $state('auto'); // 'auto', '%', 'rem', 'px'
	let blockMarginTop = $state(0);
	let blockMarginTopUnit = $state('auto'); // 'auto', '%', 'rem', 'px'

	const htmlValue = $derived(`
  <section
	class="relative not-prose isolate overflow-hidden bg-gray-100 px-6 py-10 lg:px-8 rounded-3xl shadow"
    style="padding-inline: ${sectionPaddingInlineUnit !== 'auto' ? `${sectionPaddingInline}${sectionPaddingInlineUnit}` : '2.5rem'}; padding-block: ${sectionPaddingBlockUnit !== 'auto' ? `${sectionPaddingBlock}${sectionPaddingBlockUnit}` : '2rem' }; margin-top: ${blockMarginTopUnit !== 'auto' ? `${blockMarginTop}${blockMarginTopUnit}` : '8rem'}"
>
	<div
		class="hidden sm:absolute sm:-top-10 sm:right-1/2 sm:-z-10 sm:mr-10 sm:block sm:transform-gpu sm:blur-3xl"
	>
		<div
			class="aspect-[1097/845] w-[68.5625rem] bg-gradient-to-tr from-[#ff4694] to-[#776fff] opacity-20"
			style="clip-path: polygon(74.1% 44.1%, 100% 61.6%, 97.5% 26.9%, 85.5% 0.1%, 80.7% 2%, 72.5% 32.5%, 60.2% 62.4%, 52.4% 68.1%, 47.5% 58.3%, 45.2% 34.5%, 27.5% 76.7%, 0.1% 64.9%, 17.9% 100%, 27.6% 76.8%, 76.1% 97.7%, 74.1% 44.1%)"
		></div>
	</div>
	<div
		class="absolute -top-52 left-1/2 -z-10 -translate-x-1/2 transform-gpu blur-3xl sm:top-[-28rem] sm:ml-16 sm:translate-x-0 sm:transform-gpu"
	>
		<div
			class="aspect-[1097/845] w-[68.5625rem] bg-gradient-to-tr from-[#ff4694] to-[#776fff] opacity-20"
			style="clip-path: polygon(74.1% 44.1%, 100% 61.6%, 97.5% 26.9%, 85.5% 0.1%, 80.7% 2%, 72.5% 32.5%, 60.2% 62.4%, 52.4% 68.1%, 47.5% 58.3%, 45.2% 34.5%, 27.5% 76.7%, 0.1% 64.9%, 17.9% 100%, 27.6% 76.8%, 76.1% 97.7%, 74.1% 44.1%)"
		></div>
	</div>

	<div class="mx-auto max-w-2xl lg:max-w-4xl">
		<div class="flex justify-center items-center">
			<img src="${quoteCompanyLogo}" alt="Company Logo" style="height: ${quoteCompanyLogoHeightUnit === 'auto' ? 'auto' : `${quoteCompanyLogoHeight}${quoteCompanyLogoHeightUnit}`}; width: ${quoteCompanyLogoWidthUnit === 'auto' ? 'auto' : `${quoteCompanyLogoWidth}${quoteCompanyLogoWidthUnit}`}" class="mx-auto flex-none" />
		</div>

		<figure style="margin:0; margin-top: ${blockMarginUnit !== 'auto' ? `${blockMargin}${blockMarginUnit}` : '1.75rem'}">
			<blockquote
        style="border: none; padding: 0; font-style: normal; ${quoteTextSizeUnit !== 'auto' ? `font-size: ${quoteTextSize}${quoteTextSizeUnit};` : ''} ${quoteLineHeight ? `line-height: ${quoteLineHeight};` : ''}"
				class="text-center text-xl font-semibold leading-8 text-gray-900 sm:leading-9"
			>
				<p>
					${quote}
				</p>
			</blockquote>
			<figcaption style="margin-top: ${blockMarginUnit !== 'auto' ? `${blockMargin}${blockMarginUnit}` : '1.75rem'}; gap: ${authorBlockGapUnit !== 'auto' ? `${authorBlockGap}${authorBlockGapUnit}` : '12px'}" class="flex items-center justify-center">
				<picture>
					<source srcset="${quoteAuthorImage} 64w, ${quoteAuthorImage} 128w" />
					<img
						src="${quoteAuthorImage}"
						srcset="${quoteAuthorImage} 64w, ${quoteAuthorImage} 128w"
						alt="${quoteAuthor}, ${quoteAuthorTitle}"
						class="mx-auto h-10 w-10 rounded-full"
                        style="height: ${quoteAuthorImageHeightUnit === 'auto' ? 'auto' : `${quoteAuthorImageHeight}${quoteAuthorImageHeightUnit}`}; width: ${quoteAuthorImageWidthUnit === 'auto' ? 'auto' : `${quoteAuthorImageWidth}${quoteAuthorImageWidthUnit}`}"
						width="560"
						height="560"
						loading="lazy"
						decoding="async"
					/>
				</picture>

				<div class="text-base">
					<div class="font-semibold text-gray-900"
                        style="${quoteAuthorTextSizeUnit !== 'auto' ? `font-size: ${quoteAuthorTextSize}${quoteAuthorTextSizeUnit};` : ''} ${quoteAuthorLineHeight ? `line-height: ${quoteAuthorLineHeight};` : ''}"
                    >${quoteAuthor}</div>
					<div class="text-gray-900"
                        style="${quoteAuthorTitleTextSizeUnit !== 'auto' ? `font-size: ${quoteAuthorTitleTextSize}${quoteAuthorTitleTextSizeUnit};` : ''} ${quoteAuthorTitleLineHeight ? `line-height: ${quoteAuthorTitleLineHeight};` : ''}"
                    >${quoteAuthorTitle}</div>
				</div>
			</figcaption>
		</figure>
	</div>
</section>`);
</script>

<section class="flex gap-2 flex-col-reverse">
	<div class="mb-5 flex flex-col gap-4">
		<h2 class="text-center text-2xl font-semibold text-gray-900">Modify data for this Quote</h2>
		<div class="flex flex-wrap items-center justify-between gap-3">
			<Label for="image">Logo Image URL</Label>
			<div class="flex w-[80%] flex-col gap-3">
				<Input
					class="w-full max-w-3xl"
					id="image"
					bind:value={quoteCompanyLogo}
					placeholder="Enter image url"
				/>
				<div class="flex gap-3">
					<div class="flex w-1/2 items-end gap-3">
						<div class="flex w-full flex-col items-center justify-center gap-2">
							{#if quoteCompanyLogoHeightUnit === 'auto'}
								<p class="text-sm text-gray-500">
									Height is set to auto, height will be adjusted automatically
								</p>
							{:else}
								<Input class="w-14" bind:value={quoteCompanyLogoHeight} />
							{/if}
							<Slider type="single" max={100} step={1} bind:value={quoteCompanyLogoHeight} />
						</div>
						<Select.Root type="single" bind:value={quoteCompanyLogoHeightUnit}>
							<Select.Trigger>{quoteCompanyLogoHeightUnit}</Select.Trigger>
							<Select.Content>
								<Select.Item value="auto">auto</Select.Item>
								<Select.Item value="%">%</Select.Item>
								<Select.Item value="rem">rem</Select.Item>
								<Select.Item value="px">px</Select.Item>
							</Select.Content>
						</Select.Root>
					</div>
					<div class="flex w-1/2 items-end gap-3">
						<div class="flex w-full flex-col items-center justify-center gap-2">
							{#if quoteCompanyLogoWidthUnit === 'auto'}
								<p class="text-sm text-gray-500">
									Width is set to auto, width will be adjusted automatically
								</p>
							{:else}
								<Input class="w-14" bind:value={quoteCompanyLogoWidth} />
							{/if}
							<Slider type="single" max={100} step={1} bind:value={quoteCompanyLogoWidth} />
						</div>
						<Select.Root type="single" bind:value={quoteCompanyLogoWidthUnit}>
							<Select.Trigger>{quoteCompanyLogoWidthUnit}</Select.Trigger>
							<Select.Content>
								<Select.Item value="auto">auto</Select.Item>
								<Select.Item value="%">%</Select.Item>
								<Select.Item value="rem">rem</Select.Item>
								<Select.Item value="px">px</Select.Item>
							</Select.Content>
						</Select.Root>
					</div>
				</div>
			</div>
		</div>
		<Separator class="w-full" />
		<div class="flex flex-wrap items-center justify-between gap-3">
			<Label for="image">Author Image URL</Label>
			<div class="flex w-[80%] flex-col gap-3">
				<Input
					class="w-full max-w-3xl"
					id="image"
					bind:value={quoteAuthorImage}
					placeholder="Enter image url"
				/>

				<div class="flex gap-3">
					<div class="flex w-1/2 items-end gap-3">
						<div class="flex w-full flex-col items-center justify-center gap-2">
							{#if quoteAuthorImageHeightUnit === 'auto'}
								<p class="text-sm text-gray-500">
									Height is set to auto, height will be adjusted automatically
								</p>
							{:else}
								<Input class="w-14" bind:value={quoteAuthorImageHeight} />
							{/if}
							<Slider type="single" max={100} step={1} bind:value={quoteAuthorImageHeight} />
						</div>
						<Select.Root type="single" bind:value={quoteAuthorImageHeightUnit}>
							<Select.Trigger>{quoteAuthorImageHeightUnit}</Select.Trigger>
							<Select.Content>
								<Select.Item value="auto">auto</Select.Item>
								<Select.Item value="%">%</Select.Item>
								<Select.Item value="rem">rem</Select.Item>
								<Select.Item value="px">px</Select.Item>
							</Select.Content>
						</Select.Root>
					</div>
					<div class="flex w-1/2 items-end gap-3">
						<div class="flex w-full flex-col items-center justify-center gap-2">
							{#if quoteAuthorImageWidthUnit === 'auto'}
								<p class="text-sm text-gray-500">
									Width is set to auto, width will be adjusted automatically
								</p>
							{:else}
								<Input class="w-14" bind:value={quoteAuthorImageWidth} />
							{/if}
							<Slider type="single" max={100} step={1} bind:value={quoteAuthorImageWidth} />
						</div>
						<Select.Root type="single" bind:value={quoteAuthorImageWidthUnit}>
							<Select.Trigger>{quoteAuthorImageWidthUnit}</Select.Trigger>
							<Select.Content>
								<Select.Item value="auto">auto</Select.Item>
								<Select.Item value="%">%</Select.Item>
								<Select.Item value="rem">rem</Select.Item>
								<Select.Item value="px">px</Select.Item>
							</Select.Content>
						</Select.Root>
					</div>
				</div>
			</div>
		</div>
		<Separator class="w-full" />
		<div class="flex flex-wrap items-center justify-between gap-3">
			<Label for="author">Quate author</Label>
			<div class="flex w-[80%] flex-col gap-3">
				<Input
					class="w-full max-w-3xl"
					id="author"
					bind:value={quoteAuthor}
					placeholder="Enter quate author"
				/>

				<div class="flex gap-3"></div>
				<div class="flex gap-3">
					<div class="flex w-1/2 items-end gap-3">
						<div class="flex w-full flex-col items-center justify-center gap-2">
							{#if quoteAuthorTextSizeUnit === 'auto'}
								<p class="text-sm text-gray-500">
									Text size is set to auto, text size will be adjusted automatically
								</p>
							{:else}
								<Input class="w-14" bind:value={quoteAuthorTextSize} />
								<Slider
									type="single"
									max={quoteAuthorTextSizeUnit === '%'
										? 100
										: quoteAuthorTextSizeUnit === 'rem'
											? 5
											: 1000}
									step={0.25}
									bind:value={quoteAuthorTextSize}
								/>
							{/if}
						</div>
						<Select.Root type="single" bind:value={quoteAuthorTextSizeUnit}>
							<Select.Trigger>{quoteAuthorTextSizeUnit}</Select.Trigger>
							<Select.Content>
								<Select.Item value="auto">auto</Select.Item>
								<Select.Item value="%">%</Select.Item>
								<Select.Item value="rem">rem</Select.Item>
								<Select.Item value="px">px</Select.Item>
							</Select.Content>
						</Select.Root>
					</div>
					<div class="flex w-1/2 items-end gap-3">
						<div class="flex w-full flex-col items-center justify-center gap-2">
							{#if quoteAuthorTextSizeUnit === 'auto'}
								<p class="text-sm text-gray-500">
									Line height is set to auto, line height will be adjusted automatically
								</p>
							{:else}
								<Input class="w-14" bind:value={quoteAuthorLineHeight} />
								<Slider type="single" max={2} step={0.1} bind:value={quoteAuthorLineHeight} />
							{/if}
						</div>
					</div>
				</div>
			</div>
		</div>
		<Separator class="w-full" />
		<div class="flex flex-wrap items-center justify-between gap-3">
			<Label for="job">Quate author title</Label>
			<div class="flex w-[80%] flex-col gap-3">
				<Input
					class="w-full max-w-3xl"
					id="job"
					bind:value={quoteAuthorTitle}
					placeholder="Enter quate author title"
				/>

				<div class="flex gap-3">
					<div class="flex w-1/2 items-end gap-3">
						<div class="flex w-full flex-col items-center justify-center gap-2">
							{#if quoteAuthorTitleTextSizeUnit === 'auto'}
								<p class="text-sm text-gray-500">
									Text size is set to auto, text size will be adjusted automatically
								</p>
							{:else}
								<Input class="w-14" bind:value={quoteAuthorTitleTextSize} />
								<Slider
									type="single"
									max={quoteAuthorTitleTextSizeUnit === '%'
										? 100
										: quoteAuthorTitleTextSizeUnit === 'rem'
											? 5
											: 1000}
									step={0.25}
									bind:value={quoteAuthorTitleTextSize}
								/>
							{/if}
						</div>
						<Select.Root type="single" bind:value={quoteAuthorTitleTextSizeUnit}>
							<Select.Trigger>{quoteAuthorTitleTextSizeUnit}</Select.Trigger>
							<Select.Content>
								<Select.Item value="auto">auto</Select.Item>
								<Select.Item value="%">%</Select.Item>
								<Select.Item value="rem">rem</Select.Item>
								<Select.Item value="px">px</Select.Item>
							</Select.Content>
						</Select.Root>
					</div>
					<div class="flex w-1/2 items-end gap-3">
						<div class="flex w-full flex-col items-center justify-center gap-2">
							{#if quoteAuthorTitleTextSizeUnit === 'auto'}
								<p class="text-sm text-gray-500">
									Line height is set to auto, line height will be adjusted automatically
								</p>
							{:else}
								<Input class="w-14" bind:value={quoteAuthorTitleLineHeight} />
								<Slider type="single" max={2} step={0.1} bind:value={quoteAuthorTitleLineHeight} />
							{/if}
						</div>
					</div>
				</div>
			</div>
		</div>
		<Separator class="w-full" />

		<div class="flex flex-wrap items-center justify-between gap-3">
			<Label for="text">Quate text</Label>
			<div class="flex w-[80%] flex-col gap-3">
				<Textarea
					class="w-full max-w-3xl"
					id="text"
					bind:value={quote}
					placeholder="Enter Quate text"
				/>

				<div class="flex gap-3">
					<div class="flex w-1/2 items-end gap-3">
						<div class="flex w-full flex-col items-center justify-center gap-2">
							{#if quoteTextSizeUnit === 'auto'}
								<p class="text-sm text-gray-500">
									Text size is set to auto, text size will be adjusted automatically
								</p>
							{:else}
								<Input class="w-14" bind:value={quoteTextSize} />
								<Slider
									type="single"
									max={quoteTextSizeUnit === '%' ? 100 : quoteTextSizeUnit === 'rem' ? 5 : 1000}
									step={0.25}
									bind:value={quoteTextSize}
								/>
							{/if}
						</div>
						<Select.Root type="single" bind:value={quoteTextSizeUnit}>
							<Select.Trigger>{quoteTextSizeUnit}</Select.Trigger>
							<Select.Content>
								<Select.Item value="auto">auto</Select.Item>
								<Select.Item value="%">%</Select.Item>
								<Select.Item value="rem">rem</Select.Item>
								<Select.Item value="px">px</Select.Item>
							</Select.Content>
						</Select.Root>
					</div>
					<div class="flex w-1/2 items-end gap-3">
						<div class="flex w-full flex-col items-center justify-center gap-2">
							{#if quoteTextSizeUnit === 'auto'}
								<p class="text-sm text-gray-500">
									Line height is set to auto, line height will be adjusted automatically
								</p>
							{:else}
								<Input class="w-14" bind:value={quoteLineHeight} />
								<Slider type="single" max={2} step={0.1} bind:value={quoteLineHeight} />
							{/if}
						</div>
					</div>
				</div>
			</div>
		</div>

		<Separator class="w-full" />

		<div class="flex flex-wrap items-center justify-between gap-3">
			<Label for="margins">Spaces between general blocks</Label>
			<div class="flex w-[80%] flex-col gap-3">
				<div class="flex w-full items-end gap-3">
					<div class="flex w-full flex-col items-center justify-center gap-2">
						{#if blockMarginUnit === 'auto'}
							<p class="text-sm text-gray-500">
								Text size is set to auto, text size will be adjusted automatically
							</p>
						{:else}
							<Input class="w-14" bind:value={blockMargin} />
							<Slider
								type="single"
								max={blockMarginUnit === '%' ? 100 : blockMarginUnit === 'rem' ? 5 : 1000}
								step={0.25}
								bind:value={blockMargin}
							/>
						{/if}
					</div>
					<Select.Root type="single" bind:value={blockMarginUnit}>
						<Select.Trigger>{blockMarginUnit}</Select.Trigger>
						<Select.Content>
							<Select.Item value="auto">auto</Select.Item>
							<Select.Item value="%">%</Select.Item>
							<Select.Item value="rem">rem</Select.Item>
							<Select.Item value="px">px</Select.Item>
						</Select.Content>
					</Select.Root>
				</div>
			</div>
		</div>

		<Separator class="w-full" />

		<div class="flex flex-wrap items-center justify-between gap-3">
			<Label for="margins">Margin above block</Label>
			<div class="flex w-[80%] flex-col gap-3">
				<div class="flex w-full items-end gap-3">
					<div class="flex w-full flex-col items-center justify-center gap-2">
						{#if blockMarginTopUnit === 'auto'}
							<p class="text-sm text-gray-500">
								Margin is set to auto, margin will be adjusted automatically
							</p>
						{:else}
							<Input class="w-14" bind:value={blockMarginTop} />
							<Slider
								type="single"
								max={blockMarginTopUnit === '%' ? 100 : blockMarginTopUnit === 'rem' ? 5 : 1000}
								step={0.25}
								bind:value={blockMarginTop}
							/>
						{/if}
					</div>
					<Select.Root type="single" bind:value={blockMarginTopUnit}>
						<Select.Trigger>{blockMarginTopUnit}</Select.Trigger>
						<Select.Content>
							<Select.Item value="auto">auto</Select.Item>
							<Select.Item value="%">%</Select.Item>
							<Select.Item value="rem">rem</Select.Item>
							<Select.Item value="px">px</Select.Item>
						</Select.Content>
					</Select.Root>
				</div>
			</div>
		</div>

		<Separator class="w-full" />

		<div class="flex flex-wrap items-center justify-between gap-3">
			<Label for="margins">Spaces in author block</Label>
			<div class="flex w-[80%] flex-col gap-3">
				<div class="flex w-full items-end gap-3">
					<div class="flex w-full flex-col items-center justify-center gap-2">
						{#if authorBlockGapUnit === 'auto'}
							<p class="text-sm text-gray-500">
								Text size is set to auto, text size will be adjusted automatically
							</p>
						{:else}
							<Input class="w-14" bind:value={authorBlockGap} />
							<Slider
								type="single"
								max={authorBlockGapUnit === '%' ? 100 : authorBlockGapUnit === 'rem' ? 5 : 1000}
								step={0.25}
								bind:value={authorBlockGap}
							/>
						{/if}
					</div>
					<Select.Root type="single" bind:value={authorBlockGapUnit}>
						<Select.Trigger>{authorBlockGapUnit}</Select.Trigger>
						<Select.Content>
							<Select.Item value="auto">auto</Select.Item>
							<Select.Item value="%">%</Select.Item>
							<Select.Item value="rem">rem</Select.Item>
							<Select.Item value="px">px</Select.Item>
						</Select.Content>
					</Select.Root>
				</div>
			</div>
		</div>

		<Separator class="w-full" />

		<div class="flex flex-wrap items-center justify-between gap-3">
			<Label for="margins">Main block paddings</Label>
			<div class="flex w-[80%] flex-col gap-3">
				<div class="flex w-1/2 items-end gap-3">
					<div class="flex w-full flex-col items-center justify-center gap-2">
						{#if sectionPaddingInlineUnit === 'auto'}
							<p class="text-sm text-gray-500">
								Text size is set to auto, text size will be adjusted automatically
							</p>
						{:else}
							<Input class="w-14" bind:value={sectionPaddingInline} />
							<Slider
								type="single"
								max={sectionPaddingInlineUnit === '%'
									? 100
									: sectionPaddingInlineUnit === 'rem'
										? 5
										: 1000}
								step={0.25}
								bind:value={sectionPaddingInline}
							/>
						{/if}
					</div>
					<Select.Root type="single" bind:value={sectionPaddingInlineUnit}>
						<Select.Trigger>{sectionPaddingInlineUnit}</Select.Trigger>
						<Select.Content>
							<Select.Item value="auto">auto</Select.Item>
							<Select.Item value="%">%</Select.Item>
							<Select.Item value="rem">rem</Select.Item>
							<Select.Item value="px">px</Select.Item>
						</Select.Content>
					</Select.Root>
				</div>
				<div class="flex w-1/2 items-end gap-3">
					<div class="flex w-full flex-col items-center justify-center gap-2">
						{#if sectionPaddingBlockUnit === 'auto'}
							<p class="text-sm text-gray-500">
								Text size is set to auto, text size will be adjusted automatically
							</p>
						{:else}
							<Input class="w-14" bind:value={sectionPaddingBlock} />
							<Slider
								type="single"
								max={sectionPaddingBlockUnit === '%'
									? 100
									: sectionPaddingBlockUnit === 'rem'
										? 5
										: 1000}
								step={0.25}
								bind:value={sectionPaddingBlock}
							/>
						{/if}
					</div>
					<Select.Root type="single" bind:value={sectionPaddingBlockUnit}>
						<Select.Trigger>{sectionPaddingBlockUnit}</Select.Trigger>
						<Select.Content>
							<Select.Item value="auto">auto</Select.Item>
							<Select.Item value="%">%</Select.Item>
							<Select.Item value="rem">rem</Select.Item>
							<Select.Item value="px">px</Select.Item>
						</Select.Content>
					</Select.Root>
				</div>
			</div>
		</div>

		<Button onclick={() => copyToClipboard(htmlValue)} class="mx-auto" type="submit"
			>Copy to clipboard</Button
		>
	</div>
	<div class="relative flex flex-col gap-2">
		<h2 class="text-center text-lg font-bold">How it will look like</h2>

		<div class="prose sticky top-10 left-0 mx-auto h-fit w-full max-w-3xl">
			{@html htmlValue}
		</div>
	</div>
</section>
