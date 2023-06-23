<script setup>
import { ref } from 'vue'
import Header from './Header.vue'
import Layout from './Layout.vue'
import Resume from "./Resume/Index.vue";
import Movements from "./Movements.vue";

const amount = ref(null);
</script>
<template>
    <Layout>
        <template #header>
            <Header></Header>
        </template>
        <template #resume>
            <Resume :total-label="'Ahorro total'" :label="label" :total-amount="1000000" :amount="amount">
            <template #graphic>
                graphic
            </template>
            <template #action>
                action
            </template>
            </Resume>
        </template>
        <template #movements>
            <Movements />
        </template>
    </Layout>
</template>