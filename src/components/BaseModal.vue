<template>
    <div
        v-show="modalActive"
        class="absolute w-full bg-black bg-opacity-30 h-screen
        top-0 left-0 flex justify-center px-8">
        <div
        v-if="modalActive"
        class="p-4 bg-white self-start mt-32 max-w-screen-md">
            <slot />
            <button class="text-white mt-8
            bg-weather-primary py-2 px-6" @click="$emit('close-modal')">
                close
            </button>
        </div>
    </div>
</template>

<script setup>
    // defineEmits,
    // tạo ra một danh sách các sự kiện mà component con có thể phát đi
    // thông qua $emit.Điều này giúp trong việc quản lý và xác định rõ ràng các
    // sự kiện mà component con có thể tương tác với component cha
    defineEmits(["close-modal"]);
    defineProps({
        modalActive: {
            type: Boolean,
            default: false,
        }
    });
</script>

<style lang="scss" scoped>

</style>