<template>
	<div class="logo">

<g-link to="/">		
<g-image alt="Author image" class="author__image" src="~/assets/images/a-logo2.png" width="200" height="200" blur="5" />	
</g-link>
	</div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<style lang="scss">
.logo {
	text-decoration: none;
  color: var(--body-color)!important;
  font-size: .9em;

	&__image {
		vertical-align: middle;
		border-radius: 99px;
		height: 40px;
		width: 40px;
		margin-right: .5em;
	}
}
</style>
