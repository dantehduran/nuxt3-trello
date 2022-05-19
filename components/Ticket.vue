<script setup>
import { computed } from 'vue';
const props = defineProps({
	ticket: Object,
});
const levelColor = computed(() => {
	if (props.ticket.level === 'Low Level') return 'bg-green-100 text-green-700';
	if (props.ticket.level === 'Medium Level')
		return 'bg-yellow-100 text-yellow-700';
	if (props.ticket.level === 'High Level') return 'bg-red-100 text-red-700';
	return 'bg-gray-100 text-gray-700';
});
</script>
<template>
	<div
		class="bg-white p-4 mb-3 shadow-md border-x border-gray-100 rounded-md flex flex-col-reverse space-y-2 space-y-reverse relative"
	>
		<div>{{ ticket.title }}</div>
		<div class="text-gray-400 text-sm">
			{{ ticket.author }}, {{ ticket.created_at }}
		</div>
		<div class="text-gray-300 flex items-center">
			<svg
				xmlns="http://www.w3.org/2000/svg"
				class="h-5 w-5"
				viewBox="0 0 20 20"
				fill="currentColor"
			>
				<path
					fill-rule="evenodd"
					d="M18 13V5a2 2 0 00-2-2H4a2 2 0 00-2 2v8a2 2 0 002 2h3l3 3 3-3h3a2 2 0 002-2zM5 7a1 1 0 011-1h8a1 1 0 110 2H6a1 1 0 01-1-1zm1 3a1 1 0 100 2h3a1 1 0 100-2H6z"
					clip-rule="evenodd"
				/>
			</svg>
			<span class="text-gray-400 font-semibold">{{
				ticket.comments_count
			}}</span>
		</div>
		<div
			:class="
				'absolute top-4 right-4  font-semibold text-sm px-3 rounded-full ' +
				levelColor
			"
		>
			{{ ticket.level }}
		</div>
	</div>
</template>
