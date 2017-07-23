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
                <li v-bind:class="{active:currentTab===0}">
                    <Production v-bind:profile="profile" />
                </li>
                <li v-bind:class="{active:currentTab===1}">
                    <h3>学习经历</h3>
                </li>
                <li v-bind:class="{active:currentTab===2}">
                    <JobHistory v-bind:workHistory="workHistory"/>
                </li>
                <li v-bind:class="{active:currentTab===3}">
                    <h3>项目经历</h3>
                </li>
                <li v-bind:class="{active:currentTab===4}">
                    <h3>技能掌握</h3>
                </li>
                <li v-bind:class="{active:currentTab===5}">
                    <h3>联系方式</h3>
                </li>
            </ol>
        </div>
    </div>
</template>

<script>
import Production from './Production'
import JobHistory from './JobHistory'

export default {
    components: {
        Production,JobHistory
    },
    data() {
        return {
            currentTab: 0,
            icons: ["production", "study", "job", "skills", "project", "phone"],
            profile: {
                name: "",
                city: "",
                birth: ""
            },
            workHistory: [
                { company: '', content: '' }
            ]
        }
    },
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
        overflow: auto;
        width: 100%;
        li {
            display: none;
            &.active {
                display: block;
            }
        }
    }
}
</style>

