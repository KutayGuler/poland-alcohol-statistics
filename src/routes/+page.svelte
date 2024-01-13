<script lang="ts">
  import { shuffle } from 'd3';
  import PieChart from './PieChart.svelte';

  let data = [
    { index: 0, name: 'Xd', value: 5 },
    { index: 1, name: 'lmao', value: 5 },
    { index: 2, name: 'oo', value: 90 }
  ];

  let parent_array: any[] = [];

  for (let i = 0; i < 100; i++) {
    if (i < 58) {
      parent_array.push('twa-angry-face');
    } else if (i < 94) {
      parent_array.push('twa-face-with-raised-eyebrow');
    } else {
      parent_array.push('twa-face-with-rolling-eyes');
    }

    parent_array = parent_array
      .map((value) => ({ value, sort: Math.random() }))
      .sort((a, b) => a.sort - b.sort)
      .map(({ value }) => value);
  }
</script>

<main class="flex flex-col items-center justify-center bg-[#1f1b18]">
  <section class="flex flex-col gap-24 p-8 max-w-3xl bg-[#1f1b18] text-[#fbe7d1] z-10">
    <div>
      <h1 class="text-center">Alcohol in numbers</h1>
      <p>
        In the period from January 1 to December 31 in 2011, there were 32,802 traffic incidents in
        the Lesser Poland region.
      </p>
    </div>
    <div>
      <h3>Traffic Accident Perpetrators</h3>
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
      <div class="flex flex-row gap-24 w-full h-full pt-20 pb-12 items-center justify-center pr-8">
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
      <div>
        <p>at home (45%)</p>
        <p>at home with someone else (30%)</p>
        <p>under a cloud (25%)</p>
      </div>
    </div>
    <div>
      <h3>From where did the alcohol drunk the first time come from?</h3>
      <div class="flex flex-row gap-6 pt-10 pb-16 -rotate-3">
        <img
          class="w-20 h-20"
          src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/49/Pacman.svg/228px-Pacman.svg.png"
        />
        <div class="flex flex-col justify-center gap-2">
          <div class="flex flex-row gap-2 items-center">
            {#each { length: 17 } as _}
              <i class="twa twa-tropical-drink text-2xl"></i>
            {/each}
          </div>
          <div class="flex flex-rowh-2 w-full">
            <div class="flex flex-row gap-2 bg-[#ea861a] h-4 w-[56%]"></div>
            <div class="flex flex-row gap-2 bg-[#84cb5d] h-4 w-[36%]"></div>
            <div class="flex flex-row gap-2 bg-[#06b6d4] h-4 w-[12%]"></div>
          </div>
        </div>
      </div>
      <div class="flex flex-col gap-2 text-xl">
        {#each [[50, 'bg-[#ea861a]', ' It was bought by an adult'], [38, 'bg-[#84cb5d]', 'The teenager was given it by an adult, e.g., at a home celebration'], [12, 'bg-[#06b6d4]', 'It was bought by a minor']] as [percentage, bg, text]}
          <div class="flex flex-row items-center gap-2">
            <span class="w-4 h-4 {bg}"></span><b>{percentage}% - </b>
            {text}
          </div>
        {/each}
      </div>
    </div>
    <div>
      <h3>Influence</h3>
      <p class="pb-6">
        According to the total number of teenagers surveyed, the biggest influence on whether they
        drink alcohol is:
      </p>
      <div class="flex flex-row gap-8 h-full items-end">
        {#each [['PARENTS', 44, 100], ['FRIENDS', 42, 100], ['ADVERTISEMENT', 8, 49], ['SIBLINGS', 6, 46]] as [name, percentage, width]}
          <div class="flex flex-col w-1/4 items-center">
            <div
              class="flex justify-center relative w-full h-40 border-gray-300 border-4 rounded-b-full border-t-0 bg-gray-50/10"
            >
              <div
                class="absolute bottom-0 w-1/4 bg-[#a0041e] h-24 border-gray-300 rounded-b-full -z-10"
                style="height: {percentage}%; width: {width}%;"
              ></div>
            </div>
            <div class="bg-gray-300 h-40 w-1.5"></div>
            <div class="bg-gray-300 w-1/2 h-1"></div>
            <div class="montserrat text-lg">
              {name} <br /> <span>({percentage}%)</span>
            </div>
          </div>
        {/each}
      </div>
    </div>
    <div>
      <h3>Parental attitudes and underage drinking</h3>
      <!-- TODO: chart -->
      <div class="flex flex-row items-start justify-center pt-4 gap-4">
        <div class="bg-amber-500 w-96 h-[600px] border-gray-200 border-[16px] border-t-0 relative">
          <div class="bg-white w-full h-20"></div>
          {#each parent_array as _, i}
            {@const row = (i % 10) * 32.5}
            {@const column = Math.floor(i / 10) * 50}
            <i
              class="absolute text-2xl twa {_}"
              style="left: {5 + Math.random() * 20 + row}px; bottom: {5 +
                Math.random() * 20 +
                column}px;"
            ></i>
          {/each}
          <div
            class="border-gray-200 w-72 h-80 border-l-0 border-[32px] rounded-full -z-10 absolute top-36 left-64 rounded-t-3xl"
          ></div>
        </div>
        <div class="flex flex-col w-72 items-start justify-start text-xl">
          <p><i class="twa twa-angry-face"></i> Strongly against <b>58%</b></p>
          <p>
            <i class="twa twa-face-with-raised-eyebrow"></i> Against but with exceptions
            <b>36%</b>
          </p>
          <p>
            <i class="twa twa-face-with-rolling-eyes"></i> Sometimes you can turn a blind eye
            <b>6%</b>
          </p>
        </div>
      </div>
    </div>
    <!-- <PieChart {data}></PieChart> -->
  </section>
</main>

<style>
  h1 {
    @apply text-6xl;
  }

  h3 {
    @apply text-4xl;
  }

  p {
    @apply text-xl;
  }
</style>
