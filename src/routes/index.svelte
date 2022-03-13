<script>
	let word = '';
	let definitions = [];

	let questions = {};

	function save(word, definitions, questions) {
        
    }
</script>

<h1 class="text-5xl font-bold font-mono">Hello world!</h1>

<input bind:value={word} placeholder="enter a word" />
<input bind:value={definitions} placeholder="enter a definition" />

<form class="w-full max-w-sm">
	<div class="md:flex md:items-center mb-6">
		<div class="md:w-1/3">
			<label
				class="block text-gray-500 font-bold md:text-right mb-1 md:mb-0 pr-4"
				for="inline-full-name"
			>
				Full Name
			</label>
		</div>
		<div class="md:w-2/3">
			<input
				class="bg-gray-200 appearance-none border-2 border-gray-200 rounded w-full py-2 px-4 text-gray-800 leading-tight focus:outline-none focus:bg-white focus:border-blue-500"
				id="inline-full-name"
				type="text"
				placeholder="Enter a word"
                bind:value={word}
			/>
		</div>
	</div>
	<div class="md:flex md:items-center mb-6">
		<div class="md:w-1/3">
			<label
				class="block text-gray-500 font-bold md:text-right mb-1 md:mb-0 pr-4"
				for="inline-password"
			>
				Password
			</label>
		</div>
		<div class="md:w-2/3">
			<input
				class="bg-gray-200 appearance-none border-2 border-gray-200 rounded w-full py-2 px-4 text-gray-800 leading-tight focus:outline-none focus:bg-white focus:border-blue-500"
				id="inline-password"
				type="text"
				placeholder="Enter definition(s)"
                bind:value={definitions}
			/>
		</div>
	</div>
	<div class="md:flex md:items-center">
		<div class="md:w-1/3" />
		<div class="md:w-2/3">
			<button
				class="bg-blue-500 text-white font-bold py-2 px-10 border-b-4 border-blue-700 hover:border-blue-600 rounded-full active:bg-blue-600 active:scale-95 transition-transform active:border-blue-1000"
                on:click={() => save(word, definitions, questions)}
			>
				Button
			</button>
		</div>
	</div>
</form>

<!--
    TO DO:
        finish save() function
            detect if both input boxes are filled
                if not, tell the user
            void any CAPITALIZATION and punctuation
            detect multiple definitions
            add question to the hub

        add hub for preexisting questions
            able to delete questions
-->