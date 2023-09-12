<script>
	let watchtime = 0;
	let followage = 0;
	let subscribage = 0;

	let rt_wt = 100;
	let rt_fw = 500;
	let rt_sb = 1000;

	let total = 0;

	$: total = watchtime * rt_wt + followage * rt_fw + subscribage * rt_sb;
</script>

<main>
	<h1 class="text-2xl font-bold text-center text-gray-800 dark:text-gray-100 md:text-3xl">Stream DND Campaign Converter Thing</h1>

	<form class="my-6 grid grid-cols-2 gap-4">
		<div class="flex flex-col text-sm mb-2">
			<label for="watchtime" class="font-bold mb-2 text-gray-800 dark:text-gray-100">Hours Watchtime</label>
			<input type="number" id="watchtime" bind:value={watchtime} class="appearance-none border border-gray-200 p-2 focus:outline-none focus:border-gray-500 shadow-lg rounded-lg" />
		</div>
		<div class="flex flex-col text-sm mb-2">
			<label for="rt_wt" class="font-bold mb-2 text-gray-800 dark:text-gray-100">Hours Watchtime Rate</label>
			<input type="number" id="rt_wt" bind:value={rt_wt} class="appearance-none border border-gray-200 p-2 focus:outline-none focus:border-gray-500 shadow-lg rounded-lg" />
		</div>
		<div class="flex flex-col text-sm mb-2">
			<label for="followage" class="font-bold mb-2 text-gray-800 dark:text-gray-100">Months Following</label>
			<input type="number" id="followage" bind:value={followage} class="appearance-none border border-gray-200 p-2 focus:outline-none focus:border-gray-500 shadow-lg rounded-lg" />
		</div>
		<div class="flex flex-col text-sm mb-2">
			<label for="rt_fw" class="font-bold mb-2 text-gray-800 dark:text-gray-100">Months Following Rate</label>
			<input type="number" id="rt_fw" bind:value={rt_fw} class="appearance-none border border-gray-200 p-2 focus:outline-none focus:border-gray-500 shadow-lg rounded-lg" />
		</div>
		<div class="flex flex-col text-sm mb-2">
			<label for="subscribage" class="font-bold mb-2 text-gray-800 dark:text-gray-100">Months Subscribed</label>
			<input type="number" id="subscribage" bind:value={subscribage} class="appearance-none border border-gray-200 p-2 focus:outline-none focus:border-gray-500 shadow-lg rounded-lg" />
		</div>
		<div class="flex flex-col text-sm mb-2">
			<label for="rt_sb" class="font-bold mb-2 text-gray-800 dark:text-gray-100">Months Subscribed Rate</label>
			<input type="number" id="rt_sb" bind:value={rt_sb} class="appearance-none border border-gray-200 p-2 focus:outline-none focus:border-gray-500 shadow-lg rounded-lg" />
		</div>
	</form>

	<hr />

	<p class="font-bold mb-2 text-gray-800 dark:text-gray-100 mt-5">
		Apparently, your DND XP thing is about...
	</p>

	<ul class="font-bold mb-2 text-gray-800 dark:text-gray-100">
		<li>{watchtime} &times; {rt_wt}xp/hour = {watchtime * rt_wt}xp</li>
		<li>{followage} &times; {rt_fw}xp/month = {followage * rt_fw}xp</li>
		<li>{subscribage} &times; {rt_sb}xp/month = {subscribage * rt_sb}xp</li>
	</ul>

	<p class="font-bold mb-2 text-gray-800 dark:text-gray-100 mt-5">
		For a grand total of {total}xp. Congrats! =D
	</p>

</main>

