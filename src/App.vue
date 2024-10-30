<template>
    <div class="app-container">
        <h1>Форма оформлення їжі</h1>

        <custom-input v-model:dishName="dishName" v-model:quantity="quantity" v-model:size="size" />

        <div class="order-details">
            <div>
                <span>Назва страви: </span><strong>{{ dishName }}</strong>
            </div>
            <div>
                <span>Кількість порцій: </span><strong>{{ quantity }}</strong>
            </div>
            <div>
                <span>Розмір порції: </span><strong>{{ size }}</strong>
            </div>
        </div>
    </div>
</template>

<script>
import CustomInput from './components/CustomInput.vue'

export default {
    components: {
        CustomInput,
    },
    data() {
        return {
            dishName: '',
            quantity: 0,
            size: 'M', // Початкове значення розміру
        }
    },
}
</script>

<style scoped>
div {
    max-width: 400px;
    margin: 20px auto;
}
</style>
