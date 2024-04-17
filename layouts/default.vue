<template>
    <header class="sticky top-0 z-10 flex justify-between border-b-[1px] border-b-neutral-300 px-10 py-5 backdrop-blur">
        <h1 class="text-center text-5xl font-bold">文字数カウンター</h1>
        <div class="flex items-center justify-center">
            <ColorModeButton />
        </div>
    </header>
    <slot />
</template>
