<script lang="ts">
  import MobileMenuButton from "../components/MobileMenuButton.svelte";
  import Tailwind from "../components/Tailwind.svelte";

  export let segment: string;
  let menuOpen = false;
</script>

<Tailwind />

<div class="bg-gray-800 pb-32">
  <nav class="bg-gray-800">
    <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
      <div class="border-b border-gray-700">
        <div class="flex items-center justify-between h-16 px-4 sm:px-0">
          <div class="flex items-center">
            <div class="flex-shrink-0">              
              <svg
                class="w-16 bg-gray-300 fill-current text-gray-800"
                viewBox="0 0 370 190"
              >
                <defs>
                  <path id="j" d="M40 40 H0 V50 H40 V40 H50 V0 H40 V40" />
                  <path
                    id="e"
                    d="M0 0 H50 V10 H0 V0 M0 20 H50 V30 H0 V20 M0 40 H50 V50 H0 V40"
                  />
                  <path id="t" d="M0 0 H50 V10 H30 V50 H20 V10 H0" />
                  <path
                    id="s"
                    d="M0 0 H50 V10 H10 V20 H50 V50 H0 V40 H40 V30 H0"
                  />
                  <path id="r" d="M10 10 H0 V50 H10 V10 H50 V0 H10 V10" />
                  <path
                    id="o"
                    fill-rule="evenodd"
                    d="M0 0 H50 V50 H0 V0 M10 10 H40 V40 H10 V10"
                  />
                  <path
                    id="b"
                    fill-rule="evenodd"
                    d="M0 0 H50 V50 H0 V0 M10 10 H40 V20 H10 V10 M10 30 H40 V40 H10 V30"
                  />

                  <mask id="jet" stroke-width="2">
                    <rect x="0" y="0" width="370" height="190" fill="white" />
                    <g transform="translate(10,10)">
                      <use xlink:href="#j" transform="translate(0,0)" />
                      <use xlink:href="#e" transform="translate(60,0)" />
                      <use xlink:href="#t" transform="translate(120,0)" />
                    </g>
                    <g transform="translate(70,70)">
                      <use xlink:href="#s" transform="translate(0,0)" />
                      <use xlink:href="#e" transform="translate(60,0)" />
                      <use xlink:href="#t" transform="translate(120,0)" />
                    </g>
                    <g transform="translate(10,130)">
                      <use xlink:href="#r" transform="translate(0,0)" />
                      <use xlink:href="#o" transform="translate(60,0)" />
                      <use xlink:href="#b" transform="translate(120,0)" />
                      <use xlink:href="#o" transform="translate(180,0)" />
                      <use xlink:href="#t" transform="translate(240,0)" />
                      <use xlink:href="#s" transform="translate(300,0)" />
                    </g>
                  </mask>
                </defs>
                <rect x="0" y="0" width="370" height="190" mask="url(#jet)" />
              </svg>
            </div>
            <div class="hidden md:block">
              <div class="ml-10 flex items-baseline space-x-4">
                <a
                  href="/"
                  class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium {segment ===
                  undefined
                    ? 'bg-gray-900 text-white'
                    : ''}"
                >
                  Home
                </a>
                <a
                  href="/biographie"
                  class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium {segment ===
                  'biographie'
                    ? 'bg-gray-900 text-white'
                    : ''}"
                >
                  Biographie
                </a>
              </div>
            </div>
          </div>

          <div class="-mr-2 flex md:hidden">
            <MobileMenuButton bind:open={menuOpen} />
          </div>
        </div>
      </div>
    </div>

    <!--
		Mobile menu, toggle classes based on menu state.

		Open: "block", closed: "hidden"
	  -->
    <div
      id="menu"
      class="{menuOpen ? 'block' : 'hidden'} border-b border-gray-700 md:hidden"
    >
      <div class="px-2 py-3 space-y-1 sm:px-3">
        <a
          href="/"
          class="text-gray-300 hover:bg-gray-700 hover:text-white block px-3 py-2 rounded-md text-base font-medium {segment ===
          undefined
            ? 'bg-gray-900 text-white'
            : ''}"
        >
          Home
        </a>
        <a
          href="/biographie"
          class="text-gray-300 hover:bg-gray-700 hover:text-white block px-3 py-2 rounded-md text-base font-medium {segment ===
          'biographie'
            ? 'bg-gray-900 text-white'
            : ''}"
        >
          Biographie
        </a>
      </div>
    </div>
  </nav>
  <header class="py-3 md:py-6 lg:py-8">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <h1 class="text-3xl font-bold text-white">{segment || 'jet.set.robots'}</h1>
    </div>
  </header>
</div>

<main class="-mt-32">
  <div class="max-w-7xl mx-auto pb-12 px-4 sm:px-6 lg:px-8">
    <div class="prose bg-white rounded-lg shadow px-5 py-6 sm:px-6">
      <slot />
    </div>
  </div>
</main>
