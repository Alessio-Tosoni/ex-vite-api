<script>
export default {
    name: "CardBirreria",
    props: {
        info: Object
    }
}
</script>

<template>
    <div class="card-wrapper">
        <div class="card">
            <div>
                <p class="mt-8">{{ info.name }}</p>
                <p class="mt-8">{{ info.city }}</p> 
                <p class="mt-8">{{ info.address_1 }}</p>
                <p class="mt-8">{{ info.phone }}</p>
            </div>
        </div>
    </div>
</template>

<style scoped>
.card-wrapper {
    padding: 1rem;
    width: calc(100% / 5);
}

.card {
    padding: 1rem;
    background-color: #eee;
    color: black;
}
</style>