<template>
    <div class="flex space-x-2 items-center">
        <div class="text-gray-500 text-xs" v-if="showNextModelLabel">Change to {{ nextMode }}</div>
        <button type="button" @mouseenter="showNextModelLabel = true" @mouseleave="showNextModelLabel = false"
            @click="toggleMode()" class="hover:bg-gray-100 dark:hover:bg-gray-600 px-2 py-1 text-gray-500">{{
                nextModeIcon }}
            {{ nextMode }}</button>
    </div>
</template>
<script setup>
const showNextModelLabel = ref(false);
const colorMode = useColorMode();

const modes = [
    'system', // 0
    'light', // 1
    'dark', // 2
];

const nextModeIcons = {
    system: '🌓',
    light: '🌕',
    dark: '🌑'
}

const nextMode = computed(() => {
    const currentModeIndex = modes.indexOf(colorMode.preference);
    return modes[(currentModeIndex + 1) % modes.length]; // Modulus untuk siklus
});

const nextModeIcon = computed(() => nextModeIcons[nextMode.value]);

const toggleMode = () => { return colorMode.preference = nextMode.value; }
</script>