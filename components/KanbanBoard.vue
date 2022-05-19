<script setup>
import lanes from '../data/lanes';
</script>
<template>
	<div class="grid grid-cols-3 gap-6">
		<div
			v-for="lane in lanes"
			:key="lane.name"
			class="border border-gray-300 rounded-md bg-gray-50"
		>
			<div
				class="bg-white border-b border-gray-300 p-4 rounded-t-md flex items-center justify-between"
			>
				<div class="text-lg font-semibold">
					{{ lane.name }}
				</div>
				<div class="flex items-center space-x-4">
					<button
						v-if="lane.name == 'Done'"
						class="text-blue-500 hover:text-blue-700 font-semibold"
					>
						Clear all
					</button>
					<span
						class="block py-1 px-3 bg-gray-200 rounded-xl text-sm font-semibold"
						>{{ lane.tickets.length }}</span
					>
				</div>
			</div>
			<div class="p-4">
				<template v-for="ticket in lane.tickets" :key="ticket.title">
					<Ticket :ticket="ticket" />
				</template>
			</div>
		</div>
	</div>
</template>
