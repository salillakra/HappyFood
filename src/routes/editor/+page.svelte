<!-- <script>
	// @ts-ignore
	import { quill } from 'svelte-quill';

	let options = {
		debug: 'info',
		modules: {
			toolbar: [
				[{ header: [1, 2, 3, 4, 5, 6, false] }],
				['bold', 'italic', 'underline', 'strike'],
				['blockquote', 'code-block'],
				[{ list: 'ordered' }, { list: 'bullet' }, { list: 'check' }],
				[{ script: 'sub' }, { script: 'super' }],
				[{ indent: '-1' }, { indent: '+1' }],
				[{ direction: 'rtl' }],
				[{ size: ['small', false, 'large', 'huge'] }],
				[{ color: [] }, { background: [] }],
				['link', 'image', 'video'],
				['font'], // Font selection
				['clean']
			]
		},
		placeholder: 'Write your blog post here...',
		readOnly: false,
		theme: 'snow'
	};

	let content = { html: '', text: '' };
</script>

<svelte:head>
	<link href="//cdn.quilljs.com/1.3.6/quill.snow.css" rel="stylesheet" />
</svelte:head>

<main>
	<h1>SVELTE-QUILL</h1>
	<div class="editor" use:quill={options} on:text-change={(e) => (content = e.detail)} />

	<br />
	Resulting HTML:

	<div class="home">
		{@html content.html}
	</div>
</main>

<style>
	.home img {
		width: 20rem;
	}
</style> -->
