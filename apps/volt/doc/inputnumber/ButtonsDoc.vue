<template>
    <DocSectionText v-bind="$attrs">
        <p>Spinner buttons are enabled using the <i>showButtons</i> property and layout is defined with the <i>buttonLayout</i>.</p>
    </DocSectionText>
    <div class="card flex flex-wrap gap-4">
        <div class="flex-auto">
            <label for="stacked-buttons" class="font-bold block mb-2"> Stacked </label>
            <InputNumber v-model="value1" inputId="stacked-buttons" showButtons mode="currency" currency="USD" fluid />
        </div>

        <div class="flex-auto">
            <label for="minmax-buttons" class="font-bold block mb-2"> Min-Max Boundaries </label>
            <InputNumber v-model="value2" inputId="minmax-buttons" mode="decimal" showButtons :min="0" :max="100" fluid />
        </div>
        <div class="flex-auto">
            <label for="horizontal-buttons" class="font-bold block mb-2"> Horizontal with Step </label>
            <InputNumber v-model="value3" inputId="horizontal-buttons" showButtons buttonLayout="horizontal" :step="0.25" mode="currency" currency="EUR" fluid>
                <template #incrementbuttonicon>
                    <span class="pi pi-plus" />
                </template>
                <template #decrementbuttonicon>
                    <span class="pi pi-minus" />
                </template>
            </InputNumber>
        </div>
    </div>
    <DocSectionCode :code="code" />
</template>

<script setup lang="ts">
import InputNumber from '@/volt/InputNumber.vue';
import { ref } from 'vue';

const value1 = ref(20);
const value2 = ref(25);
const value3 = ref(10.5);

const code = ref(`
<template>
    <div class="card flex flex-wrap gap-4">
        <div class="flex-auto">
            <label for="stacked-buttons" class="font-bold block mb-2"> Stacked </label>
            <InputNumber v-model="value1" inputId="stacked-buttons" showButtons mode="currency" currency="USD" fluid />
        </div>

        <div class="flex-auto">
            <label for="minmax-buttons" class="font-bold block mb-2"> Min-Max Boundaries </label>
            <InputNumber v-model="value2" inputId="minmax-buttons" mode="decimal" showButtons :min="0" :max="100" fluid />
        </div>
        <div class="flex-auto">
            <label for="horizontal-buttons" class="font-bold block mb-2"> Horizontal with Step </label>
            <InputNumber v-model="value3" inputId="horizontal-buttons" showButtons buttonLayout="horizontal" :step="0.25" mode="currency" currency="EUR" fluid>
                <template #incrementbuttonicon>
                    <span class="pi pi-plus" />
                </template>
                <template #decrementbuttonicon>
                    <span class="pi pi-minus" />
                </template>
            </InputNumber>
        </div>
    </div>
</template>

<script setup lang="ts">
import InputNumber from '@/volt/InputNumber.vue';
import { ref } from 'vue';

const value1 = ref(20);
const value2 = ref(25);
const value3 = ref(10.5);
<\/script>
`);
</script>
