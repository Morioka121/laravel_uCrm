<script setup>
import GuestLayout from '@/Layouts/GuestLayout.vue'
import InputLabel from '@/Components/InputLabel.vue'
import TextInput from '@/Components/TextInput.vue'
</script>

<template>
<GuestLayout>
    <InputLabel value="件名">タイトル</INputLabel>
    <TextInput modelValue="初期値です"></TextInput>
</GuestLayout>
</template>