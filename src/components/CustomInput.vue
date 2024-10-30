<template>
    <div>
        <label>
            Введіть назву страви:
            <input v-model="dishNameInput" placeholder="Назва страви" />
        </label>

        <label>
            Введіть кількість порцій:
            <input type="number" v-model="quantityInput" placeholder="Кількість порцій" />
        </label>

        <label>
            Виберіть розмір порції:
            <select v-model="sizeInput">
                <option value="S">S</option>
                <option value="M">M</option>
                <option value="L">L</option>
            </select>
        </label>
    </div>
</template>

<script>
export default {
    name: 'CustomInput',
    props: {
        dishName: {
            type: String,
            default: '',
        },
        quantity: {
            type: Number,
            default: 0,
        },
        size: {
            type: String,
            default: 'M', // За замовчуванням значення M
        },
    },
    computed: {
        dishNameInput: {
            get() {
                return this.dishName
            },
            set(newValue) {
                this.$emit('update:dishName', newValue)
            },
        },
        quantityInput: {
            get() {
                return this.quantity
            },
            set(newValue) {
                this.$emit('update:quantity', Number(newValue))
            },
        },
        sizeInput: {
            get() {
                return this.size
            },
            set(newValue) {
                this.$emit('update:size', newValue)
            },
        },
    },
}
</script>

<style lang="css" scoped>
label {
    display: block;
    margin-bottom: 10px;
}
input,
select {
    margin-left: 10px;
}
</style>
