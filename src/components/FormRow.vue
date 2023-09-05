<template>
    <div>
        <p>FORM ROW INPUT PLACEHOLDER</p>
        <input :type="props.field.type" />
        <FormRowError v-if="!valid">Error ocurred !!!</FormRowError>
    </div>
</template>

<script setup>
import { computed } from 'vue';
import FormRowError from './FormRowError.vue';

const props = defineProps({
    field: {
        type: Object,
        required: true
    }
});

const valid = computed(() => true);

</script>

<style lang="scss" scoped>
</style>