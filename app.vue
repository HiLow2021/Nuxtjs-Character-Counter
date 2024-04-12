<script setup lang="ts">
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
        <div class="flex flex-col gap-8">
            <h1 class="text-5xl text-center font-bold">文字数カウンター</h1>
            <div class="flex flex-col w-[800px] h-[530px] bg-neutral-200 shadow-lg p-8 gap-4">
                <div class="bg-white rounded">
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
            <div class="flex flex-col w-[800px] bg-neutral-200 shadow-lg p-8 gap-4">
                <div class="flex flex-col gap-6">
                    <div class="flex justify-between items-center basis-1/2 bg-white rounded h-16 p-4">
                        <div class="text-2xl">総文字数</div>
                        <div class="text-3xl text-blue-500">{{ resultText.length }} 文字</div>
                    </div>
                    <div class="flex justify-between items-center basis-1/2 bg-white rounded h-16 p-4">
                        <div class="text-2xl">総文字数 (空白・改行なし)</div>
                        <div class="text-3xl text-blue-500">{{ resultText.replace(/\s+?/g, '').length }} 文字</div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
