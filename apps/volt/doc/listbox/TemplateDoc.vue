<template>
    <DocSectionText v-bind="$attrs">
        <p>Custom content for an option is displayed with the <i>option</i> slot that takes an option as a parameter. Additional available templating sections are <i>filter</i> and <i>optionGroup</i>.</p>
    </DocSectionText>
    <div class="card flex justify-center">
        <Listbox v-model="selectedCountry" :options="countries" optionLabel="name" class="w-full md:w-56" listStyle="max-height:250px">
            <template #option="slotProps">
                <div class="flex items-center">
                    <img :alt="slotProps.option.name" src="https://primefaces.org/cdn/primevue/images/flag/flag_placeholder.png" :class="`flag flag-${slotProps.option.code.toLowerCase()} mr-2`" style="width: 18px" />
                    <span>{{ slotProps.option.name }}</span>
                </div>
            </template>
        </Listbox>
    </div>
    <DocSectionCode :code="code" />
</template>

<script setup>
import Listbox from '@/volt/listbox';
import { ref } from 'vue';

const selectedCountry = ref(null);
const countries = ref([
    { name: 'Australia', code: 'AU' },
    { name: 'Brazil', code: 'BR' },
    { name: 'China', code: 'CN' },
    { name: 'Egypt', code: 'EG' },
    { name: 'France', code: 'FR' },
    { name: 'Germany', code: 'DE' },
    { name: 'India', code: 'IN' },
    { name: 'Japan', code: 'JP' },
    { name: 'Spain', code: 'ES' },
    { name: 'United States', code: 'US' }
]);

const code = ref(`
<template>
    <div class="card flex justify-center">
        <Listbox v-model="selectedCountry" :options="countries" optionLabel="name" class="w-full md:w-56" listStyle="max-height:250px">
            <template #option="slotProps">
                <div class="flex items-center">
                    <img :alt="slotProps.option.name" src="https://primefaces.org/cdn/primevue/images/flag/flag_placeholder.png" :class="\`flag flag-\${slotProps.option.code.toLowerCase()} mr-2\`" style="width: 18px" />
                    <span>{{ slotProps.option.name }}</span>
                </div>
            </template>
        </Listbox>
    </div>
</template>

<script setup>
import Listbox from '@/volt/listbox';
import { ref } from 'vue';

const selectedCountry = ref(null);
const countries = ref([
    { name: 'Australia', code: 'AU' },
    { name: 'Brazil', code: 'BR' },
    { name: 'China', code: 'CN' },
    { name: 'Egypt', code: 'EG' },
    { name: 'France', code: 'FR' },
    { name: 'Germany', code: 'DE' },
    { name: 'India', code: 'IN' },
    { name: 'Japan', code: 'JP' },
    { name: 'Spain', code: 'ES' },
    { name: 'United States', code: 'US' }
]);
<\/script>
`);
</script>
