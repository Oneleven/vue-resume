<template>
    <div class="editor">
        <nav>
            <ol class="icons">
                <li v-for="i in [0,1,2,3,4,5]" v-bind:class="{active:currentTab===i}" v-on:click="currentTab=i">
                    <svg class="icon" aria-hidden="true">
                        <use v-bind:xlink:href="`#icon-${icons[i]}`"></use>
                    </svg>
                </li>
            </ol>
        </nav>
        <div class="tab_content">
            <ol>
                <li v-for="i in [0,1,2,3,4,5]" v-bind:class="{active:currentTab===i}">tab1</li>
            </ol>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            currentTab: 0,
            icons: ["production", "study", "job", "skills", "project", "phone"]
        }
    }
}
</script>


<style lang="scss">
.editor {
    border: 1px solid black;
    height: 100%;
    display: flex;
    nav {
        background-color: black;
        width: 80px;
        >.icons>li {
            text-align: center;
            padding: 16px 0;
            >.icon {
                height: 24px;
                width: 24px;
                fill: white;
            }
            &.active {
                background: white;
                >.icon {
                    fill: black;
                }
            }
        }
    }
    .tab_content {
        li {
            display: none;
            &.active {
                display: block;
            }
        }
    }
}
</style>

