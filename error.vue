<template>

    <NuxtLayout>
        <section class="container mx-auto max-w-2xl text-center">
            <h1 class=" font-bold text-9xl mb-8 mt-14">
                Oops {{ error.statusCode }}
            </h1>
            <h2>{{ error.statusMessage }}</h2>

        </section>
    </NuxtLayout>

</template>

<script setup>
defineProps({ error: Object });
</script>