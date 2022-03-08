<template>
	<div class="card">
		<h1>{{title}}</h1>
		<p>{{description}}</p>
	</div>
</template>
<script>
export default {
	name: 'CardFilm',
	props: ['title', 'description']
}
</script>