<template>
<div class="loader__parent" :class="{ background: activeBackground }">
	<div class="loader" />
</div>
</template>

<script>
export default {
	name: 'Spinner',
	props: ['activeBackground']
};
</script>

<style lang="scss" scoped>
.background {
	background-color: $spinner-background;
}
.loader__parent {
	width: 100vw;
	height: 100vh;
	display: flex;
	justify-content: center;
	align-items: center;
	position: absolute;
}

.loader,
.loader:after {
	border-radius: 50%;
	width: 8em;
	height: 8em;
}
.loader {
	// margin: 60px auto;
	font-size: 15px;
	// position: relative;
	// text-indent: -9999em;
	border-top: 1.1em solid $opacity-half;
	border-right: 1.1em solid $opacity-half;
	border-bottom: 1.1em solid $opacity-half;
	border-left: 1.1em solid $white;
	-webkit-transform: translateZ(0);
	-ms-transform: translateZ(0);
	transform: translateZ(0);
	-webkit-animation: load8 1.1s infinite linear;
	animation: load8 1.1s infinite linear;
}
@-webkit-keyframes load8 {
	0% {
		-webkit-transform: rotate(0deg);
		transform: rotate(0deg);
	}
	100% {
		-webkit-transform: rotate(360deg);
		transform: rotate(360deg);
	}
}
@keyframes load8 {
	0% {
		-webkit-transform: rotate(0deg);
		transform: rotate(0deg);
	}
	100% {
		-webkit-transform: rotate(360deg);
		transform: rotate(360deg);
	}
}
</style>
