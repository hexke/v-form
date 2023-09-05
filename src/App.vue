<template>
    <Suspense>
        <TheForm :form="form"/>
        <template #fallback>
            <TheSpinner />
        </template>
    </Suspense>
</template>

<script setup>
import { toRef } from 'vue';
import formJSON from './assets/form.json';
import TheForm from './components/TheForm.vue';
import TheSpinner from './components/TheSpinner.vue';

const form = toRef(formJSON);

function InitializeForm(){
    throw new Error("Not implemented!");
}
function SaveForm(){
    throw new Error("Not implemented!");
}
</script>

<style scoped>

</style>
