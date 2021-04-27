<template>
    <div class="...">
        <img class="mb-2 space-image" :src="space.image" alt="">
        <div class="grid grid-cols-2">
            <div class="...">
                <p>{{ space.name }}</p>
            </div>
            <div class="...">
                <DotsVerticalIcon v-on:click="toggleDropdown()" class="float-right h-5 w-5"/>
                <div v-bind:class="{'hidden': !dropdownPopoverShow, 'block': dropdownPopoverShow}" class="bg-blueGray-500 text-base z-50 float-left py-2 list-none text-left rounded shadow-lg mt-1" style="min-width:12rem" ref="popoverDropdownRef">
                    <a href="#pablo" class="text-sm py-2 px-4 font-normal block w-full whitespace-nowrap bg-transparent">
                        Edit
                    </a>
                    <a href="#pablo" class="text-sm py-2 px-4 font-normal block w-full whitespace-nowrap bg-transparent">
                        Embed
                    </a>
                    <a href="#pablo" class="text-sm py-2 px-4 font-normal block w-full whitespace-nowrap bg-transparent">
                       Delete
                    </a>
                </div>
            </div>
        </div>
    </div>
</template>
<script lang="ts">
    import { defineComponent } from 'vue';
    import { DotsVerticalIcon } from '@heroicons/vue/outline';
    type Space = {
        name: string
        image: string
    }

    export default defineComponent({
        components: { DotsVerticalIcon },
        name: 'SpaceItem',
        props: {
            space: {
                type: Object as () => Space,
                required: true
            }
        },
        data: function () {
            return {
                dropdownPopoverShow: false
            }
        },
        methods: {
            toggleDropdown: function(){
                if(this.dropdownPopoverShow){
                    this.dropdownPopoverShow = false;
                } else {
                    this.dropdownPopoverShow = true;
                }
            }
        }
    });
</script>