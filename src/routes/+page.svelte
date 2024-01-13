<script lang="ts">
  import { shuffle } from 'd3';
  import PieChart from './PieChart.svelte';

  let data = [
    { index: 0, name: '', value: 45 },
    { index: 1, name: 'lmao', value: 35 },
    { index: 2, name: 'oo', value: 25 }
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
  <section class="flex flex-col gap-48 p-8 max-w-3xl bg-[#1f1b18] text-[#fbe7d1] z-10">
    <div>
      <h1 class="text-center">Alcohol in numbers</h1>
      <p>
        In the period from January 1 to December 31 in 2011, there were 32,802 traffic incidents in
        the Lesser Poland region.
      </p>
    </div>
    <div>
      <h3>Traffic Accident Perpetrators</h3>
      <div class="w-full pt-24 pb-44 relative flex flex-row">
        <i class="top-28 left-52 absolute twa twa-oncoming-automobile text-6xl scale-[500%]"></i>
        <i class="top-48 left-[432px] absolute twa twa-person-walking text-6xl"></i>
        <i class="top-48 left-[524px] absolute twa twa-red-question-mark text-6xl scale-50"></i>
        <div class="absolute z-10 left-[400px] top-6">
          <p><b>77%</b> Drivers</p>
          <p class="pl-2"><b>15%</b> Pedestrians</p>
          <p class="pl-4"><b>8%</b> Others</p>
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
      <!-- <h3>Youth who admitted to trying alcohol</h3> -->
      <div class="flex flex-row gap-4">
        <div class="flex flex-col gap-4">
          <div class="relative w-80 h-[320px] bg-sky-800 flex items-end">
            <i class="twa twa-cloud absolute top-4 left-4 text-9xl"></i>
            <div class="flex flex-row relative">
              <i class="twa twa-person-standing text-9xl"></i>
              <i
                style="transform: scale(-1, 1);"
                class="absolute twa twa-beer-mug text-3xl bottom-16 right-2"
              ></i>
            </div>
          </div>
          <div class="w-80 h-64 bg-indigo-800 flex items-end">
            <div class="relative flex flex-row w-full">
              <i class="twa twa-couch-and-lamp text-9xl"></i>
              <i class="absolute right-16 twa twa-person-standing text-9xl"></i>
              <i class="absolute -right-8 twa twa-man-standing text-9xl"></i>
              <i class="absolute twa twa-clinking-beer-mugs text-4xl bottom-16 right-16"></i>
            </div>
          </div>
        </div>
        <div class="flex flex-col gap-4">
          <div class="w-80 h-96 bg-emerald-800 flex items-end">
            <div class="flex flex-row relative w-full">
              <i class="twa twa-couch-and-lamp text-9xl"></i>
              <i class="twa twa-person-standing text-9xl"></i>
              <i
                style="transform: scale(-1, 1);"
                class="absolute twa twa-beer-mug text-3xl bottom-16 right-8"
              ></i>
            </div>
          </div>
          <div class="flex flex-col w-80">
            <h4 class="text-3xl pb-3">Youth who admitted to trying alcohol</h4>
            <p><b>45%</b> At home</p>
            <p><b>30%</b> At home with someone else</p>
            <p><b>25%</b> Under a cloud</p>
          </div>
        </div>
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
            <span class="w-4 h-4 {bg}"></span><b>{percentage}%</b>
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
          <p><i class="twa twa-angry-face"></i> <b>58%</b> Strongly against</p>
          <p>
            <i class="twa twa-face-with-raised-eyebrow"></i> <b>36%</b> Against but with exceptions
          </p>
          <p>
            <i class="twa twa-face-with-rolling-eyes"></i> <b>6%</b> Sometimes you can turn a blind eye
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
