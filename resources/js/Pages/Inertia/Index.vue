<script setup>
import { Link } from "@inertiajs/vue3";

defineProps({ blogs: Array })
</script>

<template>
    <div v-if="$page.props.flash.message" class="bg-blue-300">{{ $page.props.flash.message }}</div>
    <ul>
        <li v-for="blog in blogs" :key="blog.id">
            件名：
            <Link class="text-blue-400" :href="route('inertia.show', { id: blog.id })">{{ blog.title }}</Link>
            本文：{{ blog.content }}
        </li>
    </ul>
    <div class="mt-2">
        <Link :href="route('inertia.create')" as="button" type="button" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">新規作成</Link>
    </div>
</template>