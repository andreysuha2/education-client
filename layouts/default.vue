<template>
    <div class="app">
        <app-menu class="app--menu"/>
        <div class="app--wrapper">
            <div class="app--content">
                <app-header class="app--header"/>
                <div class="app--page">
                    <Nuxt />
                </div>
            </div>
            <app-footer class="app--footer"/>
        </div>
    </div>
</template>

<script>
import AppHeader from "@globalComponents/AppHeader";
import AppFooter from "@globalComponents/AppFooter";
import AppMenu from "@globalComponents/AppMenu";

export default {
    comments: {
        "app-header": AppHeader,
        "app-footer": AppFooter,
        "app-menu": AppMenu
    }
};
</script>

<style lang="scss" scoped>
.app {
    display: flex;
    min-height: 100%;

    &--wrapper {
        display: flex;
        flex-direction: column;
        width: 100%;
        min-height: 100%;
    }

    &--content {
        flex: 1 0 auto;
    }

    &--footer {
        flex: 0 0 auto;
    }
}
</style>

<style lang="scss">
.app {
    &--header, &--footer {
        padding: 10px;
    }

    &--header {
        border-bottom: 1px solid #000;
    }

    &--footer {
        border-top: 1px solid #000;
    }

    &--menu {
        border-right: 1px solid #000;
    }
}
</style>