<template>
    <div>
        <p>{{ props.label }}</p>
        <hr>
        <FormRow v-for="field in fields" :key="field.name" :field="field"/>
    </div>
</template>

<script setup>
import FormRow from './FormRow.vue';

const props = defineProps({
    name: {
        type: String,
        required: true,
    },
    label: {
        type: String,
        required: true,
    },
    fields: {
        type: Array,
        required: true,
    }
});

console.log(props.fields);

</script>

<style lang="scss" scoped>
div {
    margin: 30px 0;
    background-color: rgb(255, 212, 212);
}
p {
    font-size: 24px;
    font-weight: 500;
    text-transform: uppercase;
}
</style>