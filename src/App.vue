<template>
  <div class="min-h-screen bg-gray-200 text-gray-900">
    <div class="container mx-auto px-4">
      <h2 class="font-bold text-xl pt-2">Menu (Dropdown)</h2>
      <div class="mt-4">
        <Menu>
          <MenuButton class="flex items-center bg-blue-500 text-white rounded-md px-4 py-2">
            <span>More</span>
            <ChevronDownIcon class="h-5 w-5 ml-2" />
            <!-- <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 ml-2" viewBox="0 0 20 20" fill="currentColor">
              <path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd" />
            </svg> -->
          </MenuButton>

          <transition
            enter-active-class="transition duration-200 ease-out"
            enter-from-class="transform scale-75 opacity-0"
            enter-to-class="transform scale-100 opacity-100"
            leave-active-class="transition duration-100 ease-out"
            leave-from-class="transform scale-100 opacity-100"
            leave-to-class="transform scale-75 opacity-0"
          >
          <MenuItems class="absolute bg-white shadow-md rounded-lg flex flex-col focus:outline-none w-56 divide-y divide-gray-100 origin-top-left mt-2">
            <div class="px-1 py-1">
              <MenuItem v-slot="{ active }">
                <button
                  class="w-full flex items-center rounded-md px-2 py-2"
                  :class='{ "bg-blue-500 text-white": active }'
                >
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15.232 5.232l3.536 3.536m-2.036-5.036a2.5 2.5 0 113.536 3.536L6.5 21.036H3v-3.572L16.732 3.732z" />
                  </svg>
                  <span class="ml-2">Edit</span>
                </button>
              </MenuItem>
              <MenuItem v-slot="{ active }">
                <button
                  class="w-full flex items-center rounded-md px-2 py-2"
                  :class='{ "bg-blue-500 text-white": active }'
                >
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 16H6a2 2 0 01-2-2V6a2 2 0 012-2h8a2 2 0 012 2v2m-6 12h8a2 2 0 002-2v-8a2 2 0 00-2-2h-8a2 2 0 00-2 2v8a2 2 0 002 2z" />
                  </svg>
                  <span class="ml-2">Duplicate</span>
                </button>
              </MenuItem>
            </div>

            <div class="px-1 py-1">
              <MenuItem v-slot="{ active }">
                <button
                  class="w-full flex items-center rounded-md px-2 py-2"
                  :class='{ "bg-blue-500 text-white": active }'
                >
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 8h14M5 8a2 2 0 110-4h14a2 2 0 110 4M5 8v10a2 2 0 002 2h10a2 2 0 002-2V8m-9 4h4" />
                  </svg>
                  <span class="ml-2">Archive</span>
                </button>
              </MenuItem>

              <MenuItem v-slot="{ active }">
                <button
                  class="w-full flex items-center rounded-md px-2 py-2"
                  :class='{ "bg-blue-500 text-white": active }'
                >
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 11.5V14m0-2.5v-6a1.5 1.5 0 113 0m-3 6a1.5 1.5 0 00-3 0v2a7.5 7.5 0 0015 0v-5a1.5 1.5 0 00-3 0m-6-3V11m0-5.5v-1a1.5 1.5 0 013 0v1m0 0V11m0-5.5a1.5 1.5 0 013 0v3m0 0V11" />
                  </svg>
                  <span class="ml-2">Move</span>
                </button>
              </MenuItem>
            </div>

            <div class="px-1 py-1">
              <MenuItem v-slot="{ active, disabled }" disabled>
                <button
                  class="w-full flex items-center rounded-md px-2 py-2"
                  :class='{ "bg-blue-500 text-white": active, "opacity-50 cursor-not-allowed" : disabled }'
                >
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 14l2-2m0 0l2-2m-2 2l-2-2m2 2l2 2m7-2a9 9 0 11-18 0 9 9 0 0118 0z" />
                  </svg>
                  <span class="ml-2">Destroy</span>
                </button>
              </MenuItem>
              <MenuItem v-slot="{ active }">
                <button
                  class="w-full flex items-center rounded-md px-2 py-2"
                  :class='{ "bg-blue-500 text-white": active }'
                >
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 14l2-2m0 0l2-2m-2 2l-2-2m2 2l2 2m7-2a9 9 0 11-18 0 9 9 0 0118 0z" />
                  </svg>
                  <span class="ml-2">Delete</span>
                </button>
              </MenuItem>
            </div>
          </MenuItems>
          </transition>
        </Menu>

        <div class="mt-4">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aliquam, incidunt!
        </div>
      </div>
      <div class="mt-4">
        <h2 class="font-bold text-xl pt-2">Dialog (Modal)</h2>
        <div class="mt-4">
          <button @click="openModal" class="flex items-center bg-blue-500 text-white rounded-md px-4 py-2">Open Modal</button>

          <TransitionRoot appear :show="isOpen" as="template">
            <Dialog as="div" @close="closeModal">
              <div class="fixed inset-0 z-10 overflow-y-auto">
                <div class="min-h-screen px-4 text-center">
                  <TransitionChild
                    as="template"
                    enter="duration-300 ease-out"
                    enter-from="opacity-0"
                    enter-to="opacity-100"
                    leave="duration-200 ease-in"
                    leave-from="opacity-100"
                    leave-to="opacity-0"
                  >
                    <DialogOverlay class="fixed inset-0 bg-gray-500 bg-opacity-75 transition-opacity" />
                  </TransitionChild>

                  <span class="inline-block h-screen align-middle" aria-hidden="true">
                    &#8203;
                  </span>

                  <TransitionChild
                    as="template"
                    enter="duration-300 ease-out"
                    enter-from="opacity-0 scale-95 rotate-180"
                    enter-to="opacity-100 scale-100 rotate-0"
                    leave="duration-200 ease-in"
                    leave-from="opacity-100 scale-100"
                    leave-to="opacity-0 scale-95"
                  >
                    <div
                      class="inline-block w-full max-w-md p-6 my-8 overflow-hidden text-left align-middle transition-all transform bg-white shadow-xl rounded-2xl"
                    >
                      <button @click="closeModal" class="absolute top-3 right-3">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                        </svg>
                      </button>
                      <DialogTitle
                        as="h3"
                        class="text-lg font-medium leading-6 text-gray-900"
                      >
                        Payment successful for your order
                      </DialogTitle>
                      <div class="mt-2">
                        <p class="text-sm text-gray-500">
                          Your payment has been successfully submitted. We’ve sent your
                          an email with all of the details of your order. lorem400
                        </p>
                      </div>

                      <div class="mt-4">
                        <button
                          type="button"
                          class="inline-flex justify-center px-4 py-2 text-sm font-medium text-blue-900 bg-blue-100 border border-transparent rounded-md hover:bg-blue-200 focus-visible:ring-2 focus-visible:ring-offset-2 focus-visible:ring-blue-500"
                          @click="closeModal"
                        >
                          Got it, thanks!
                        </button>
                      </div>
                    </div>
                  </TransitionChild>
                </div>
              </div>
            </Dialog>
          </TransitionRoot>
        </div>
      </div>
      <div class="mt-4">
        <h2 class="font-bold text-xl pt-2">Radio Group</h2>
        <RadioGroup v-model="plan" class="max-w-md mt-8">
          <RadioGroupLabel class="font-bold">Plan</RadioGroupLabel>
          <div class="space-y-4 mt-4">
            <RadioGroupOption v-slot="{ checked }" value="startup" class="bg-white rounded-md shadow">
              <div
                class="flex items-center justify-between rounded-md px-4 py-4"
                :class="checked ? 'bg-blue-500 text-white' : ''"
              >
                <div>
                  <div class="font-bold">Startup</div>
                  <div class="text-sm">12GB/6 CPUs &middot; 160GB SSD disk</div>
                </div>
                <div v-show="checked">
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                  </svg>
                </div>
              </div>
            </RadioGroupOption>

            <RadioGroupOption v-slot="{ checked }" value="business" class="bg-white rounded-md shadow">
              <div
                class="flex items-center justify-between rounded-md px-4 py-4"
                :class="checked ? 'bg-blue-500 text-white' : ''"
              >
                <div>
                  <div class="font-bold">Business</div>
                  <div class="text-sm">16GB/8 CPUs &middot; 250GB SSD disk</div>
                </div>
                <div v-show="checked">
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                  </svg>
                </div>
              </div>
            </RadioGroupOption>

            <RadioGroupOption v-slot="{ checked }" value="enterprise" class="bg-white rounded-md shadow">
              <div
                class="flex items-center justify-between rounded-md px-4 py-4"
                :class="checked ? 'bg-blue-500 text-white' : ''"
              >
                <div>
                  <div class="font-bold">Enterprise</div>
                  <div class="text-sm">32GB/12 CPUs &middot; 500GB SSD disk</div>
                </div>
                <div v-show="checked">
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                  </svg>
                </div>
              </div>
            </RadioGroupOption>

          </div>
        </RadioGroup>
      </div>

      <div class="mt-4">
        <h2 class="font-bold text-xl pt-2">Alternate Radio Group</h2>
        <RadioGroup v-model="gameSelection" class="font-retro max-w-md mt-8">
          <RadioGroupLabel class="font-bold">Video Game Menu</RadioGroupLabel>
          <div class="space-y-4 mt-4">
            <RadioGroupOption v-slot="{ checked }" value="new game" class="text-center focus:outline-none cursor-pointer">
              <div
                class="border border-transparent px-4 py-4"
                :class="checked ? 'border-gray-500' : ''"
              >
                <div>
                  New Game
                </div>

              </div>
            </RadioGroupOption>

            <RadioGroupOption v-slot="{ checked }" value="load game" class="text-center focus:outline-none cursor-pointer">
              <div
                class="border border-transparent px-4 py-4"
                :class="checked ? 'border-gray-500' : ''"
              >
                <div>
                  Load Game
                </div>

              </div>
            </RadioGroupOption>

            <RadioGroupOption v-slot="{ checked }" value="settings" class="text-center focus:outline-none cursor-pointer">
              <div
                class="border border-transparent px-4 py-4"
                :class="checked ? 'border-gray-500' : ''"
              >
                <div>
                  Settings
                </div>

              </div>
            </RadioGroupOption>





          </div>
        </RadioGroup>
      </div>
    </div>
  </div>
</template>

<script>
  import { Menu, MenuButton, MenuItems, MenuItem, TransitionRoot,
  TransitionChild,
  Dialog,
  DialogOverlay,
  DialogTitle, RadioGroup,
    RadioGroupLabel,
    RadioGroupOption, } from "@headlessui/vue";

  import { ChevronDownIcon } from '@heroicons/vue/solid'

  export default {
    components: {
      Menu,
      MenuButton,
      MenuItems,
      MenuItem,
      ChevronDownIcon,
      TransitionRoot,
      TransitionChild,
      Dialog,
      DialogOverlay,
      DialogTitle,
      RadioGroup,
      RadioGroupLabel,
      RadioGroupOption,
    },

    data() {
      return {
        isOpen: false,
        plan: 'startup',
        gameSelection: 'new game',
      }
    },
    methods: {
      closeModal() {
        this.isOpen = false
      },
      openModal() {
        this.isOpen = true
      },
    }
  };
</script>
