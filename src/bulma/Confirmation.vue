<template>
    <core-confirmation>
        <template #default>
            <slot/>
        </template>
        <template #cancel="{ cancel }">
            <a class="button is-small"
                @click="cancel">
                <span class="icon is-small">
                    <fa :icon="faXmark"/>
                </span>
            </a>
        </template>
        <template #confirm="{ confirm }">
            <a class="button is-small is-dark ml-2"
                @click="confirm">
                <span class="icon is-small">
                    <fa :icon="faCheck"/>
                </span>
            </a>
        </template>
    </core-confirmation>
</template>

<script>
import { FontAwesomeIcon as Fa } from '@fortawesome/vue-fontawesome';
import { faCheck, faXmark } from '@fortawesome/free-solid-svg-icons';
import CoreConfirmation from '../components/CoreConfirmation.vue';

export default {
    name: 'Confirmation',

    components: { Fa, CoreConfirmation },

    data: () => ({
        faCheck,
        faXmark,
    }),
};
</script>
