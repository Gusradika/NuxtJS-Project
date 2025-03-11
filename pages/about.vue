<template>
    <div>
        This page is about me.
    </div>
    <div>
        <button @click="enableCustomLayout()">Update Layout</button>
    </div>
</template>

<script setup>

// definePageMeta({
//     layout: "another",
// });
var layout = 'default';
function enableCustomLayout() {
    if (layout == "default") {
        layout = 'another';
        setPageLayout(layout);
    } else {
        layout = 'default';
        setPageLayout(layout);
    }
}


useHead({
    title: 'About'
})

</script>