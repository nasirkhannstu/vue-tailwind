<template>
  <div>
    <div class="divide-y">
      <div class="grid grid-cols-2 my-4 mx-8">
        <div class="...">
          <h1 class="text-3xl">Space</h1>
        </div>
        <div class="...">
          <select name="" class="float-right">
            <option value="ausloggen">Ausloggen</option>
          </select>
        </div>
      </div>
      <div>
        <div class="my-4 mx-8">
          <div class="grid grid-cols-2">
            <div class="...">
              <div class="inline-flex">
                <button class="active text-white-800 font-bold py-2 px-4 rounded-l">
                  <ViewGridIcon class="h-5 w-5"/>
                </button>
                <button class="bg-gray-300 hover:bg-gray-400 text-gray-800 font-bold py-2 px-4 rounded-r">
                  <ViewListIcon class="h-5 w-5"/>
                </button>
              </div>
            </div>
            <div class="...">
              <div class="relative text-gray-600 focus-within:text-gray-400 float-right">
                <span class="absolute inset-y-0 right-0 flex items-center pr-2">
                  <button type="submit" class="p-1 focus:outline-none focus:shadow-outline">
                    <SearchIcon class="h-5 w-5"/>
                  </button>
                </span>
                <input type="search" name="q" class="shadow appearance-none border rounded py-2 px-3 text-grey-darker pr-10" placeholder="Search..." autocomplete="off">
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="mx-8">
      <div class="grid grid-cols-5 gap-4">
        <SpaceItem :key="space.name" v-for="space in spaceList" :space="space"/>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { ViewGridIcon } from '@heroicons/vue/outline'
import { ViewListIcon } from '@heroicons/vue/outline'
import { SearchIcon } from '@heroicons/vue/outline'
import SpaceItem from './SpaceItem.vue';

export default defineComponent({
  components: { ViewGridIcon, ViewListIcon, SearchIcon, SpaceItem },
  name: 'HelloWorld',
  data: function () {
    return {
      spaceList: [
        {
          name: "One",
          image: 'https://cdn.pixabay.com/photo/2015/04/19/08/32/marguerite-729510__340.jpg'
        },
        {
          name: "Two",
          image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR52ZS23g2E1br6LBetzefwaU3UDIk_7h0nO5i8lSxqXbWeod8pmXgEpdk8s0EYQ7B8eNQ&usqp=CAU'
        },
        {
          name: "Three",
          image: 'https://snappygoat.com/b/420384dfe1a95cfa52c2095764f612651e383ecb'
        },
        {
          name: "Four",
          image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSAlTMNSk9xNb75pEr-1w90p8Yii4cpos6wB2gqEhGVWLO1L7CJCBqs5m9DFyjU40ZZI4g&usqp=CAU'
        }
      ],
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

<style>
  .active {background: #00AEB3; color: #fff; }
  .space-image {
    height: 180px;
    width: 100%;
  }
</style>