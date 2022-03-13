<script>
	let word = ''
	let definitions = []

	let wordInput
	let definitionInput

	let questions = {}

	let wordWarning = ''
	let definitionWarning = ''

	function save(word, definitions, questions) {
        if (word.length != 0 && definitions.length != 0) {
			if (word in questions) {
				for (let i = 0; i < definitions.length; i++) {
					questions[word].append(definitions)
				}
			}
			else {
				questions[word] = questions
			}
			wordInput.value = ''
			definitionInput.value = []
			wordWarning = ''
			definitionWarning = ''
			return
		}
		else {
			if (word.length != 0) {
				wordWarning = 'A word is needed'
			}
			if (definitions.length != 0) {
				definitionWarning = 'A definition is needed'
			}
		}
    }
</script>

<h1 class="text-5xl font-bold font-mono">Hello world!</h1>


<form class="w-full max-w-sm">
	<div class="md:flex md:items-center mb-6">
		<div class="md:w-1/3">
			<label
				class="block text-gray-500 font-bold md:text-center mb-1 md:mb-0"
				for="inline-full-name"
			>
				Word
			</label>
		</div>
		<div class="md:w-2/3">
			<input
				class="bg-gray-200 appearance-none border-2 border-gray-200 rounded w-full py-2 px-4 text-gray-800 leading-tight focus:outline-none focus:bg-white focus:border-blue-500"
				id="inline-full-name"
				type="text"
				placeholder="Enter a word"
                bind:value={word}
				bind:this={wordInput}
			/>
		</div>
	</div>
	<div class="md:flex md:items-center">
		<div class="md:w-1/3"/>
		<div class="md:w-2/3 mb-1 font-mono text-red-800">
			{wordWarning}
		</div>
	</div>
	<div class="md:flex md:items-center mb-6">
		<div class="md:w-1/3">
			<label
				class="block text-gray-500 font-bold md:text-center mb-1 md:mb-0"
				for="inline-password"
			>
				Definition(s)
			</label>
		</div>
		<div class="md:w-2/3">
			<input
				class="bg-gray-200 appearance-none border-2 border-gray-200 rounded w-full py-2 px-4 text-gray-800 leading-tight focus:outline-none focus:bg-white focus:border-blue-500"
				id="inline-password"
				type="text"
				placeholder="Enter definition(s)"
                bind:value={definitions}
				bind:this={definitionInput}
			/>
		</div>
	</div>
	<div class="md:flex md:items-center">
		<div class="md:w-1/3"/>
		<div class="md:w-2/3 mb-1 font-mono text-red-800">
			{definitionWarning}
		</div>
	</div> 
		
	<div class="md:flex md:items-center">
		<div class="md:w-1/3" />
		<div class="md:w-2/3">
			<form method=“get”> 
				<button
					type="button"
					class="bg-blue-500 text-white font-bold py-2 px-10 border-b-4 border-blue-700 hover:border-blue-600 rounded-full active:bg-blue-600 active:scale-95 transition-transform active:border-blue-1000"
					on:click={() => save(word, definitions, questions)}
				>
					Button
				</button>
			</form>
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