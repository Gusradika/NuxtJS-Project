<template>
    <!-- Prose untuk Typography -->
    <!-- prose-pre untuk coding bg -->
    <article class="prose dark:prose-invert prose-pre:bg-gray-200 dark:prose-pre:bg-gray-800 flex mx-auto">
        <ContentRenderer class="" v-if="data" :value="data" />
        <div v-else>Article not found</div>

    </article>
    <div class="container mx-auto max-w-2xl">
        <NuxtLink class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" :to="'/blog'">Back
        </NuxtLink>
    </div>
</template>
<script setup lang="ts">
const route = useRoute()
const { data: data } = await useAsyncData(route.path, () => {
    return queryCollection('content').path(route.path).first()
})

console.log(route.params.slug[0]);
console.log(data.value);
console.log("INI TITLE : " + data.value?.title);
console.log(route.path);

useHead(() => ({
    title: data.value?.title || 'Default Title',
    meta: [
        {
            name: 'description',
            content: data.value?.description || 'Default description',
        },
        {
            property: 'og:title',
            content: data.value?.title || 'Default Title',
        },
        {
            property: 'og:description',
            content: data.value?.description || 'Default description',
        },
    ],
}));

</script>
