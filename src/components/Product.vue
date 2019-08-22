<template>
    <div class="Product">
        <h3>{{ name }}</h3>
        <h5>{{ price }}</h5>
        <slot></slot>
    </div>
</template>

<script>
    export default {
        props: ['name', 'price']
    }
</script>

<style lang="css" scoped>
    .product {
        padding: 1rem;
        margin: 1rem;
        border: 1px solid #ccc;
        box-shadow: 3px 3px 8px rgba(0, 0, 0, 0.2);
    }
</style>
