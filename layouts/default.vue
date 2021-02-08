<template>
    <div class="app"
        :class="classList.app">
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
import { mapState } from "vuex";

export default {
    comments: {
        "app-header": AppHeader,
        "app-footer": AppFooter,
        "app-menu": AppMenu
    },
    computed: {
        ...mapState("app", { theme(state) { return state.themeDark ? "dark" : "light"; } }),
        classList() {
            return {
                app: {
                    "app__light": this.theme === "light",
                    "app__dark": this.theme === "dark"
                }
            };
        }
    }
};
</script>

<style lang="scss" scoped>
.app {
    display: flex;
    min-height: 100%;
    transition: color .3s ease-in-out, background-color .3s ease-in-out;

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
    &__light {
        --background-color: #{$lightBackgroundColor};
        --text-color: #{$lightTextColor};
    }

    &__dark {
        --background-color: #{$darkBackgroundColor};
        --text-color: #{$darkTextColor};
    }

    background: var(--background-color);
    color: var(--text-color);

    &--header, &--footer {
        padding: 10px;
    }

    &--header {
        border-bottom: 1px solid var(--text-color);
    }

    &--footer {
        border-top: 1px solid var(--text-color);
    }

    &--menu {
        border-right: 1px solid var(--text-color);
    }
}
</style>