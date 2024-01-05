<main class="flex flex-col items-center justify-center">
  <section class="flex flex-col gap-4 p-8 max-w-2xl">
    <div>
      <h1 class="text-center">Alcohol in numbers</h1>
      <p>
        In the period from January 1 to December 31 in 2011, there were 32,802 traffic incidents in
        the Lesser Poland region.
      </p>
    </div>
    <div>
      <h3>Trafic Accident Perpetrators</h3>
      <div>
        <div class="w-full px-6">
          <div class="flex flex-wrap gap-1">
            {#each { length: 77 } as _}
              <i class="twa twa-oncoming-automobile text-xl"></i>
            {/each}
            {#each { length: 15 } as _}
              <i class="twa twa-person-walking text-xl"></i>
            {/each}
            {#each { length: 8 } as _}
              <i class="twa twa-red-question-mark text-xl"></i>
            {/each}
          </div>
        </div>
        <div class="flex flex-row gap-40 w-full h-full py-32 pl-8">
          {#each { length: 3 } as _}
            <div class="relative">
              <i class="twa twa-melting-face text-6xl absolute -top-1"></i>
              <i class="twa twa-pouring-liquid text-6xl absolute bottom-0 -left-6"></i>
            </div>
          {/each}
          <div class="relative">
            <i class="twa twa-slightly-smiling-face text-5xl absolute -top-2"></i>
          </div>
        </div>
        <h3 class="pb-4">Influence</h3>
        <div class="flex flex-row gap-4 h-full items-end">
          {#each [['PARENTS', 44, 100], ['FRIENDS', 42, 100], ['ADVERTISEMENT', 8, 49], ['SIBLINGS', 6, 46]] as [name, percentage, width]}
            <div class="flex flex-col w-full items-center">
              <div
                class="flex justify-center relative w-full h-40 border-gray-300 border-4 rounded-b-full border-t-0"
              >
                <div
                  class="absolute bottom-0 w-1/4 bg-[#a0041e] h-24 border-gray-300 rounded-b-full -z-10"
                  style="height: {percentage}%; width: {width}%;"
                ></div>
              </div>
              <div class="bg-gray-300 h-40 w-1.5"></div>
              <div>{name}</div>
            </div>
          {/each}
        </div>
        <h3>Parental attitudes and underage drinking</h3>
      </div>
    </div>
    <section></section>
  </section>
</main>

<style>
  h1 {
    @apply text-4xl font-bold;
  }

  h3 {
    @apply text-2xl font-bold;
  }
</style>
