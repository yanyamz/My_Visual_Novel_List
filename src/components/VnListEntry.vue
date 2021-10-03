<script>
export default {
	props: {
		visual_novel: Object,
	},
}
</script>

<template>
	<div class="visual_novel">
		<div class="visual_novel__image_container">
			<img
				:src="visual_novel.image"
				alt="thumbnail"
				class="visual_novel__image"
			/>
		</div>
		<div class="visual_novel__info">
			<div class="visual_novel__heading">
				<p class="visual_novel__title">
					{{ visual_novel.title }}
				</p>
				<p class="visual_novel__rating">{{ visual_novel.rating }}%</p>
			</div>
			<p class="visual_novel__description">
				{{ visual_novel.description.substring(0, 150) }} ...
			</p>
			<div class="visual_novel__tags">
				<span
					class="visual_novel__tag"
					v-for="tag in visual_novel.tags"
					:key="tag"
				>
					{{ tag }}
				</span>
			</div>
		</div>
	</div>
</template>

<style lang="scss" scoped>
.visual_novel {
	--border-radius: 0.5rem;
	--spacing: 1rem;

	cursor: pointer;
	background: var(--color-primary-light);
	color: white;
	display: flex;
	font-size: 1.6rem;
	border-radius: var(--border-radius);
	box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.1), 0 1px 2px 0 rgba(0, 0, 0, 0.06);

	&__image_container {
		flex: 1 0 12.5rem;
		min-height: 15rem;
		border-radius: var(--border-radius) 0 0 var(--border-radius);
	}
	&__image {
		width: 100%;
		height: 100%;
		border-radius: inherit;
		object-fit: cover;
		object-position: center;
	}

	&__heading,
	&__description,
	&__tags {
		padding-left: var(--spacing);
		padding-right: var(--spacing);
	}
	&__description,
	&__tags {
		font-size: var(--font-sm);
		color: var(--color-text-secondary);
		font-weight: 200;
	}
	&__info {
		position: relative;
		flex: 1 1 100%;
		padding-top: var(--spacing);
	}
	&__heading {
		display: flex;
		justify-content: space-between;
		max-height: 5rem;
		overflow: hidden;
	}
	&__description {
		padding-top: 1rem;
		padding-bottom: 3rem;
	}
	&__tags {
		position: absolute;
		bottom: 0;
		width: 100%;
		padding-top: 0.5rem;
		padding-bottom: 0.5rem;
		background: var(--color-primary);
		border-radius: 0 0 var(--border-radius) 0;
	}
	&__tag:not(:last-child)::after {
		content: ',';
		width: 100%;
		padding-right: 0.5rem;
	}
}
</style>
