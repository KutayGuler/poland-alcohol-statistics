<main class="flex flex-col items-center justify-center">
  <section class="flex flex-col gap-32 p-8 max-w-2xl bg-[#1f1b18] text-[#fbe7d1] z-10">
    <div>
      <h1 class="text-center">Alcohol in numbers</h1>
      <p>
        In the period from January 1 to December 31 in 2011, there were 32,802 traffic incidents in
        the Lesser Poland region.
      </p>
    </div>
    <div>
      <h3>Trafic Accident Perpetrators</h3>
      <p><i class="twa twa-oncoming-automobile text-xl"></i> Drivers: 77%</p>
      <p><i class="twa twa-person-walking text-xl"></i> Pedestrians: 15%</p>
      <p><i class="twa twa-red-question-mark text-xl"></i> Others: 8%</p>
      <div class="w-full">
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
    </div>
    <div>
      <h3>Polish Teenagers and Alcohol</h3>
      <p>Three-quarters of students aged 12-17 have a history of alcohol exposure</p>
      <div class="flex flex-row gap-24 w-full h-full py-24 items-center justify-center pr-8">
        {#each { length: 3 } as _}
          <div class="relative w-fit">
            <i class="twa twa-melting-face text-5xl absolute -top-1"></i>
            <i class="twa twa-pouring-liquid text-5xl absolute bottom-0 -left-4"></i>
          </div>
        {/each}
        <div class="relative w-fit">
          <i class="twa twa-slightly-smiling-face text-4xl absolute -top-2"></i>
        </div>
      </div>
    </div>
    <div>
      <h3>Youth who admitted to trying alcohol</h3>
    </div>
    <div>
      <h3>From where did the alcohol drunk the first time come from?</h3>
    </div>
    <div>
      <h3 class="pb-4">Influence</h3>
      <p>
        According to the total number of teenagers surveyed, the biggest influence on whether they
        drink alcohol is:
      </p>
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
            <div class="bg-gray-300 w-1/2 h-1"></div>
            <div class="montserrat">
              {name} <br /> <span>({percentage}%)</span>
            </div>
          </div>
        {/each}
      </div>
    </div>
    <div>
      <h3>Parental attitudes and underage drinking</h3>
      <!-- TODO: chart -->
      <p>Strongly against - 58%</p>
      <p>Against, but with exceptions - 36%</p>
      <p>Sometimes you can turn a blind eye - 6%</p>
    </div>
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
