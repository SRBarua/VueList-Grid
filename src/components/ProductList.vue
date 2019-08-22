<template>
    <div class="product-list">

        <div class="view-bar">
            <a href="#" @click="changeView('list')">List</a> | <a href="#" @click="changeView('grid')">Grid</a>
            <hr/>
        </div>

        <div class="products" :class="{ 'grid' : gridView }">
            <product
                v-for = "product in products"
                :name="product.name"
                :price="product.price"
                :key="product.id"
                >
                    {{ product.description }}
            </product>
        </div>

    </div>
</template>

<script>
    import Product from './Product.vue'

    export default{
        components: { Product },

        methods: {
            changView(type) {
                if(type == 'grid'){
                    this.gridView = true;
                } else {
                    this.gridView = false;
                }
            }
        },

        data(){
            return {
                gridView: false,

                products: [
                    {
                        id: 1,
                        name: 'watch',
                        description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, tempor incididunt ut labore aliqua.',
                        price: 109.99
                    },
                    {
                        id: 2,
                        name: 'computer',
                        description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, tempor incididunt ut labore aliqua.',
                        price: 750.60
                    },
                    {
                        id: 3,
                        name: 'speaker',
                        description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, tempor incididunt ut labore aliqua.',
                        price: 69.99
                    },
                    {
                        id: 4,
                        name: 'headphone',
                        description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, tempor incididunt ut labore aliqua.',
                        price: 49.99
                    },
                    {
                        id: 5,
                        name: 'clock',
                        description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, tempor incididunt ut labore aliqua.',
                        price: 39.99
                    },
                    {
                        id: 6,
                        name: 'blanket',
                        description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, tempor incididunt ut labore aliqua.',
                        price: 59.99
                    },
                ]
            }
        }
    }
</script>

<style lang="scss">
        .product-list {
            padding:2rem;
            border:1px solid #ccc;
            border-radius: 4px;

            .products {
                display: flex;
                flex-direction: column;

                &.grid {
                    flex-direction: row;
                    flex-wrap: wrap;

                    .product {
                        flex-basis: 25%;
                    }
                }
            }

        }
        .view-bar {
            text-align: right;
        }
</style>
