<template>
    <div class="menu-item">
        <img
            class="menu-item__image"
            :src="imgSource"
            :alt="imgAlt"
        />
        <div>
            <h3>{{ name }}</h3>
            <p v-if="inStock">En stock</p>
            <p v-else>En rupture de stock</p>
            <div>
                <label for="add-item-quantity"
                    >Quantité : {{ quantity }}</label
                >
                <input
                    v-model.number="quantity"
                    id="add-item-quantity"
                    type="number"
                />
                <button @click="addToShoppingCart(quantity)">
                    Ajouter au panier d'achat
                </button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'MenuItem',
    props: {
        name: String,
        imgSource: String,
        imgAlt: String,
        quantity: Number,
        inStock: Boolean
    }
}
</script>

<style>
    .menu {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    }

    .menu-item {
    display: flex;
    width: 500px;
    justify-content: space-between;
    margin-bottom: 30px;
    }

    .menu-item__image {
    max-width: 300px;
    }
</style>