<script setup lang="ts">
useHead({
    title: '',
    titleTemplate: `%s - 文字数カウンター`
});
</script>

<template>
    <Body>
        <NuxtLoadingIndicator />
        <NuxtLayout>
            <NuxtPage />
        </NuxtLayout>
    </Body>
</template>
