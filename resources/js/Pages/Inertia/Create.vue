<script setup>
import { reactive } from 'vue'
import { router } from '@inertiajs/vue3'
import ValidationErrors from '@/Components/ValidationErrors.vue';

defineProps({ errors: Object })

const form = reactive({
    title: null,
    content: null,
})

const submitFunction = () => {
    router.post('/inertia', form)
}
</script>

<template>
    <ValidationErrors :errors="errors" />
    <form @submit.prevent="submitFunction">
        <input type="text" name="title" v-model="form.title"><br>
        <div v-if="errors.title">{{ errors.title }}</div>
        <input type="text" name="content" v-model="form.content"><br>
        <div v-if="errors.content">{{ errors.content }}</div>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">送信</button>
    </form>
</template>