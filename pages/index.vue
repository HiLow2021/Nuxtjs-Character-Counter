<script setup lang="ts">
useHead({
    title: '文字数カウンター',
    titleTemplate: ''
});

const text = useState('text', () => '');
const resultText = useState('resultText', () => '');

function execution() {
    resultText.value = text.value;
}

function clear() {
    text.value = '';
    resultText.value = '';
}
</script>

<template>
    <div class="flex justify-center p-10">
        <div class="flex w-full max-w-[800px] flex-col gap-8">
            <div class="flex h-[530px] flex-col gap-4 bg-neutral-200 p-8 shadow-lg dark:bg-neutral-600">
                <div class="rounded bg-white dark:bg-neutral-800">
                    <UTextarea
                        v-model="text"
                        color="primary"
                        variant="outline"
                        placeholder="文字を入力してください..."
                        size="xl"
                        :rows="16"
                    />
                </div>
                <div class="flex gap-6">
                    <div class="basis-1/2">
                        <UButton color="primary" variant="solid" block size="xl" @click="execution">実行</UButton>
                    </div>
                    <div class="basis-1/2">
                        <UButton color="primary" variant="solid" block size="xl" @click="clear">クリア</UButton>
                    </div>
                </div>
            </div>
            <div class="flex flex-col gap-4 bg-neutral-200 p-8 shadow-lg dark:bg-neutral-600">
                <div class="flex flex-col gap-6">
                    <div class="flex h-16 basis-1/2 items-center justify-between rounded bg-white p-4 dark:bg-neutral-800">
                        <div class="text-2xl">総文字数</div>
                        <div class="text-3xl text-blue-500 dark:text-blue-400">{{ resultText.length }} 文字</div>
                    </div>
                    <div class="flex h-16 basis-1/2 items-center justify-between rounded bg-white p-4 dark:bg-neutral-800">
                        <div class="text-2xl">総文字数 (空白・改行なし)</div>
                        <div class="text-3xl text-blue-500 dark:text-blue-400">{{ resultText.replace(/\s+?/g, '').length }} 文字</div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
