<script setup></script>

<template>
	<div class="container mx-auto overflow-hidden border-x border-gray-200">
		<Nav />
		<div class="flex">
			<div class="w-1/5">
				<Sidebar />
			</div>
			<div class="w-4/5 p-10">
				<ProjectTitle />
				<KanbanBoard />
			</div>
		</div>
	</div>
</template>
