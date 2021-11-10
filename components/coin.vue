<template>
 <article class="coin">
	 <img :src="coin.flag" :alt="coin.name" class="card__img">
	 <h2 class="card__title">{{ coin.name }}</h2>
	 <p class="card__copy">{{ coin.subregion }}</p>
 </article>
</template>



<script>
export default {
	props: {
		coin: Object
	}
}
</script>