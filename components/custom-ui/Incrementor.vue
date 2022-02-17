<template>
    <div class="input-group mb-3">
        <div class="input-group-prepend">
            <span role="button" class="input-group-text" @click="decrement">-</span>
        </div>
        <input type="text" :value="value" class="form-control" @input="handleInput" />
        <div class="input-group-append">
            <span v-if="unit" class="input-group-text">
                {{ unit }}
            </span>
            <span role="button" class="input-group-text" @click="increment">+</span>
        </div>
    </div>
</template>

<script>
export default {
    props: [
        'value',
        'unit'
    ],
    methods: {
        handleInput(event) {
            this.$emit("input", event.target.value);
        },
        increment() {
            let incValue = parseInt(this.value);
            this.$emit("input", ++incValue);
        },
        decrement() {
            let incValue = parseInt(this.value);
            this.$emit("input", --incValue);
        },
    }
}
</script>