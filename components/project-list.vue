<template>
    <div>
        <h2 class="text-1xl mb-10">Projects</h2>

    </div>
    <section v-if="pending">Loading...</section>
    <section v-if="error">Something went wrong... Try again!</section>
    <section v-else>
        <ul class="grid grid-cols-1 gap-4">
            <li v-for="repo in repos" :key="repo.id"
                class="border border-gray-200 rounded-sm p-4 hover:bg-gray-100 font-mono">
                <a :href="repo.html_url" target="_blank">
                    <div class="flex items-center justify-between text-sm">
                        <div class="font-semibold text-indigo-500">
                            {{ repo.html_url }}
                            <p class="text-xs font-normal text-black">
                                {{ repo.description }}
                            </p>
                        </div>
                        <div>{{ repo.stargazers_count }} </div>
                    </div>
                </a>
            </li>
        </ul>
    </section>
</template>

<script setup>
console.log("here");
const { error, pending, data } = await useFetch('https://api.github.com/users/piotr-jura-udemy/repos');

const repos = computed(
    () => {
        return data.value.filter(repo => repo.description).sort((a, b) => b.stargazers_count - a.stargazers_count);
    }
);
</script>