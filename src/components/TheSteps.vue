<template>
    <div class="form__steps">
        <div class="form__step" :class="{active: index===props.activeStepIndex}" v-for="step, index of steps" :key="step">
            <span>{{ index + 1 }}</span>{{ step }}
        </div>
    </div>
</template>

<script setup>
    const props = defineProps({
        steps: {
            type: Array,
            required: true
        },
        activeStepIndex: {
            type: Number,
            required: true
        }
    });

</script>

<style lang="scss" scoped>
.form__steps {
    display: flex;
}

.form__step {
    display: flex;
    align-items: start;

    padding: 0.5em 1em;
    color: rgb(143, 143, 143);
    border: 1px solid currentColor;
    background-color: rgb(248, 248, 248);
    font-size: 18px;

    span {
        font-size: 1.5em;
        margin-right: 5px;
    }

    &.active {
        color: grey;
        background-color: rgb(203, 203, 203);
    }
}
</style>