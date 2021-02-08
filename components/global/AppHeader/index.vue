<template>
    <header class="app-header">
        <div class="flex justify-between">
            <span>header</span>
            <div>
                <button @click="enableLightTheme">light</button>
                <button @click="enableDarkTheme">dark</button>
            </div>
        </div>
    </header>
</template>

<script>
import { mapMutations } from "vuex";

export default {
    methods: {
        ...mapMutations("app", {
            enableLightTheme: "enableLightTheme",
            enableDarkTheme: "enableDarkTheme"
        })
    }
};
</script>

<style lang="scss" scoped>
.app-header {
    border-bottom: 1px solid var(--text-color);
    padding: 10px;
    background-color: var(--primary-color);
}
</style>