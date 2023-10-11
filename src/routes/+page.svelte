<script lang="ts">
  import moment from 'moment';

  let goal = 2500;

  // Create a Moment.js object for the current date
  const currentDate = moment();

  // Create a Moment.js object for the last day of the current year (December 31st)
  const lastDayOfYear = moment().endOf('year');

  // Calculate the difference in weeks and days
  const diffInWeeks = lastDayOfYear.diff(currentDate, 'weeks');
  const diffInDays = lastDayOfYear.diff(currentDate, 'days');

  console.log(`Number of weeks left in the current year: ${diffInWeeks}`);
  console.log(`Number of days left in the current year: ${diffInDays}`);

  const year = currentDate.year();
</script>

<div class="flex w-full flex-col place-items-center gap-10">
  <h1 class="text-2xl font-bold tracking-tight">Strava Goal Tracker</h1>

  <div class="flex flex-col place-items-center">
    <p class="text-gray-500">Your goal for {year}</p>
    <h3 class="text-5xl font-bold">{goal} km</h3>
  </div>

  <p class="text-gray-500">
    There are <span class="font-bold text-black">{diffInWeeks} weeks ({diffInDays} days)</span> left
    in {year}
  </p>

  <div class="flex flex-col place-items-center">
    <p class="text-gray-500">Distance left</p>
    <h3 class="text-5xl font-bold">959.8 km</h3>
  </div>

  <div class="flex flex-col place-items-center">
    <p class="text-gray-500">To reach this goal, you'd have to bike</p>
    <h3 class="text-5xl font-bold">80.1 km</h3>
    <p class="text-gray-500">every week</p>
  </div>
</div>
