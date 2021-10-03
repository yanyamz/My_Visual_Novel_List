<template>
	<router-view />
</template>

<style lang="scss">
//GLOBAL CSS
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;1,100&display=swap');

//VARIABLES
:root {
	--color-primary: hsl(240, 1%, 15%);
	--color-primary-light: hsl(0, 0%, 18%);
	--color-text-secondary: hsla(0, 0%, 100%, 0.8);
	--font-sm: 1.2rem;
	--font-md: 1.6rem;
}

//BASE STYLE RESETTING
*,
*::before,
*::after {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}

html {
	font-size: 62.5%;
}

body {
	background: var(--color-primary);
	padding: 2rem;
	font-family: 'Poppins', sans-serif;
}

//MAPS
$breakpoints: (
	sm: 400px,
	md: 650px,
	lg: 900px,
);

//MIXINS
@mixin mq($key) {
	$size: map.get($breakpoints, $key);
	@media (min-width: $size) {
		@content;
	}
}
</style>
