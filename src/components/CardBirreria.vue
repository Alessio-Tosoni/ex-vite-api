<script>
export default {
    name: "CharacterCard",
    props: {
        info: Object
    }
}
</script>

<template>
    <div class="card-wrapper">
        <div class="card">
            <p>{{ info.name }}</p>
            
        </div>
    </div>
</template>

<style scoped>

</style>