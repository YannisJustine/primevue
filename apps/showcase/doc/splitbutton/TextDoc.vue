<template>
    <DocSectionText v-bind="$attrs">
        <p>Text buttons are displayed as textual elements.</p>
    </DocSectionText>
    <div class="card flex justify-center flex-wrap gap-4">
        <SplitButton label="Save" :model="items" @click="save" text></SplitButton>
        <SplitButton label="Save" :model="items" @click="save" text severity="secondary"></SplitButton>
        <SplitButton label="Save" :model="items" @click="save" text severity="success"></SplitButton>
        <SplitButton label="Save" :model="items" @click="save" text severity="info"></SplitButton>
        <SplitButton label="Save" :model="items" @click="save" text severity="warn"></SplitButton>
        <SplitButton label="Save" :model="items" @click="save" text severity="help"></SplitButton>
        <SplitButton label="Save" :model="items" @click="save" text severity="danger"></SplitButton>
    </div>
    <DocSectionCode :code="code" />
</template>

<script>
export default {
    data() {
        return {
            items: [
                {
                    label: 'Update',
                    command: () => {
                        this.$toast.add({ severity: 'success', summary: 'Updated', detail: 'Data Updated', life: 3000 });
                    }
                },
                {
                    label: 'Delete',
                    command: () => {
                        this.$toast.add({ severity: 'warn', summary: 'Delete', detail: 'Data Deleted', life: 3000 });
                    }
                },
                {
                    separator: true
                },
                {
                    label: 'Quit',
                    command: () => {
                        window.location.href = 'https://vuejs.org/';
                    }
                }
            ],
            code: {
                basic: `
<SplitButton label="Save" :model="items" @click="save" text></SplitButton>
<SplitButton label="Save" :model="items" @click="save" text severity="secondary"></SplitButton>
<SplitButton label="Save" :model="items" @click="save" text severity="success"></SplitButton>
<SplitButton label="Save" :model="items" @click="save" text severity="info"></SplitButton>
<SplitButton label="Save" :model="items" @click="save" text severity="warn"></SplitButton>
<SplitButton label="Save" :model="items" @click="save" text severity="help"></SplitButton>
<SplitButton label="Save" :model="items" @click="save" text severity="danger"></SplitButton>
`,
                options: `
<template>
    <div class="card flex justify-center flex-wrap gap-4">
        <Toast />
        <SplitButton label="Save" :model="items" @click="save" text></SplitButton>
        <SplitButton label="Save" :model="items" @click="save" text severity="secondary"></SplitButton>
        <SplitButton label="Save" :model="items" @click="save" text severity="success"></SplitButton>
        <SplitButton label="Save" :model="items" @click="save" text severity="info"></SplitButton>
        <SplitButton label="Save" :model="items" @click="save" text severity="warn"></SplitButton>
        <SplitButton label="Save" :model="items" @click="save" text severity="help"></SplitButton>
        <SplitButton label="Save" :model="items" @click="save" text severity="danger"></SplitButton>
    </div>
</template>

<script>
export default {
    data() {
        return {
            items: [
                {
                    label: 'Update',
                    command: () => {
                        this.$toast.add({ severity: 'success', summary: 'Updated', detail: 'Data Updated', life: 3000 });
                    }
                },
                {
                    label: 'Delete',
                    command: () => {
                        this.$toast.add({ severity: 'warn', summary: 'Delete', detail: 'Data Deleted', life: 3000 });
                    }
                },
                {
                    separator: true
                },
                {
                    label: 'Quit',
                    command: () => {
                        window.location.href = 'https://vuejs.org/';
                    }
                }
            ]
        };
    },
    methods: {
        save() {
            this.$toast.add({ severity: 'success', summary: 'Success', detail: 'Data Saved', life: 3000 });
        }
    }
}
<\/script>
`,
                composition: `
<template>
    <div class="card flex justify-center flex-wrap gap-4">
        <Toast />
        <SplitButton label="Save" :model="items" @click="save" text></SplitButton>
        <SplitButton label="Save" :model="items" @click="save" text severity="secondary"></SplitButton>
        <SplitButton label="Save" :model="items" @click="save" text severity="success"></SplitButton>
        <SplitButton label="Save" :model="items" @click="save" text severity="info"></SplitButton>
        <SplitButton label="Save" :model="items" @click="save" text severity="warn"></SplitButton>
        <SplitButton label="Save" :model="items" @click="save" text severity="help"></SplitButton>
        <SplitButton label="Save" :model="items" @click="save" text severity="danger"></SplitButton>
    </div>
</template>

<script setup>
import { useToast } from "primevue/usetoast";
const toast = useToast();

const items = [
    {
        label: 'Update',
        command: () => {
            toast.add({ severity: 'success', summary: 'Updated', detail: 'Data Updated', life: 3000 });
        }
    },
    {
        label: 'Delete',
        command: () => {
            toast.add({ severity: 'warn', summary: 'Delete', detail: 'Data Deleted', life: 3000 });
        }
    },
    {
        separator: true
    },
    {
        label: 'Quit',
        command: () => {
            window.location.href = 'https://vuejs.org/';
        }
    }
];

const save = () => {
    toast.add({ severity: 'success', summary: 'Success', detail: 'Data Saved', life: 3000 });
};
<\/script>
`
            }
        };
    },
    methods: {
        save() {
            this.$toast.add({ severity: 'success', summary: 'Success', detail: 'Data Saved', life: 3000 });
        }
    }
};
</script>
