<template>
    <nav class="font-mono">
        <ul class="flex flex-col md:flex-row md:space-x-4">
            <li>
                <NuxtLink to="/" class="link">Main</NuxtLink>
            </li>
            <li>
                <NuxtLink to="/about" class="link">About</NuxtLink>
            </li>
            <li>
                <NuxtLink to="/project" class="link">Project</NuxtLink>
            </li>
            <li>
                <NuxtLink to="/blog" class="link">Blogs</NuxtLink>
            </li>
        </ul>
    </nav>
</template>

<style scoped>
.link {
    @apply p-1 hover:bg-gray-200 font-semibold text-2xl md:text-base;
}
</style>