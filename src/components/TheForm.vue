<template>
    <TheSteps :steps="steps" :activeStepIndex="activeStep"/>
    <button @click="Prev()">prev</button>
    <button @click="Next()">next</button>
    <FormSection v-for="step, index in props.form.steps" :key="step.name" v-show="index === activeStep"
        :name="step.name"
        :label="step.label"
        :fields="step.fields"
    />
</template>

<script setup>
import { ref } from 'vue';
import TheSteps from './TheSteps.vue';
import FormSection from './FormSection.vue';

const props = defineProps({
    form: {
        type: Object,
        required: true
    }
});

const activeStep = ref(0);

const steps = props.form.steps.map(step => step.label);

const fields = ref({});

props.form.steps.forEach(step => step.fields.forEach(field => fields.value[field.name] = ''));

function Next(){
    activeStep.value++;
}
function Prev(){
    activeStep.value--;
}
</script>

<style lang="scss" scoped>
</style>