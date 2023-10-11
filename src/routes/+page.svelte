<script lang="ts">
  import moment from 'moment';

  const currentDate = moment();
  const lastDayOfYear = moment().endOf('year');
  const diffInWeeks = lastDayOfYear.diff(currentDate, 'weeks');
  const diffInDays = lastDayOfYear.diff(currentDate, 'days');

  const year = currentDate.year();

  let goal = 2500;
  let current = 1540;
  $: distanceLeft = goal - current;
  $: weeklyGoal = Math.floor(distanceLeft / diffInWeeks);
  $: dailyGoal = Math.floor(distanceLeft / (diffInWeeks * 4));
</script>

<div class="flex w-full flex-col place-items-center gap-10">
  <h1 class="text-2xl font-bold tracking-tight">Strava Goal Tracker</h1>

  <div class="flex place-content-between gap-10">
    <div class="flex flex-col place-items-center">
      <p class="text-gray-500">Your goal for {year}</p>
      <h3 class="text-5xl font-bold">{goal} km</h3>
    </div>

    <div class="flex flex-col place-items-center">
      <p class="text-gray-500">So far, you've biked</p>
      <h3 class="text-5xl font-bold">{current} km</h3>
    </div>
  </div>

  <p class="text-gray-500">
    There are <span class="font-bold text-white">{diffInWeeks} weeks ({diffInDays} days)</span> left
    in {year}
  </p>

  <div class="flex flex-col place-items-center">
    <p class="text-gray-500">Distance left</p>
    <h3 class="text-5xl font-bold">{distanceLeft} km</h3>
  </div>

  <div class="flex flex-col place-items-center">
    <p class="text-gray-500">To reach this goal, you'd have to bike</p>
    <h3 class="text-5xl font-bold">{weeklyGoal} km</h3>
    <p class="text-gray-500">every week</p>
  </div>

  <div class="flex flex-col place-items-center">
    <p class="text-gray-500">or, if you intend to ride 4 days a week,</p>
    <h3 class="text-5xl font-bold">{dailyGoal} km</h3>
    <p class="text-gray-500">every day</p>
  </div>
</div>
