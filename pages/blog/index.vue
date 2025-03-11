<template class="">
    <div class="container mx-auto max-w-2xl">
        <section>
            <ul>
                <li v-for="key in data" :key="key.id">
                    <NuxtLink :to="key.path">{{ key.title }}</NuxtLink>
                </li>
            </ul>
        </section>
    </div>
</template>
<script setup lang="ts">
const route = useRoute()
const { data: data } = await useAsyncData(route.path, () => {
    return queryCollection('content').all()
})


console.log(data.value);
console.log("INI TITLE : ");
console.log(route.path);

useHead(() => ({
    title: 'Blog',
    meta: [
        {
            name: 'description',
            content: 'Default description',
        },
        {
            property: 'og:title',
            content: 'Default Title',
        },
        {
            property: 'og:description',
            content: 'Default description',
        },
    ],
}));

</script>
