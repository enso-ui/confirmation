<template>
    <dropdown ref="dialog">
        <slot/>
        <template #popper>
            <slot name="cancel"
                :cancel="cancel"/>
            <slot name="confirm"
                :confirm="confirm"/>
        </template>
    </dropdown>
</template>

<script>
import { Dropdown } from 'v-tooltip';

export default {
    name: 'CoreConfirmation',

    components: { Dropdown },

    emits: ['cancel', 'confirm'],

    methods: {
        cancel() {
            this.$emit('cancel');
            this.hide();
        },
        confirm() {
            this.$emit('confirm');
            this.hide();
        },
        hide() {
            this.$refs.dialog.hide();
        },
    },
};
</script>
