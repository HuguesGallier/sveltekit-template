<script>
  import PrimaryCard from "$lib/components/Card/PrimaryCard.svelte";
  import Awards from "$lib/containers/homeDashboard/Awards/Awards.svelte";
  import ContributorsTable from "$lib/containers/homeDashboard/Contributors/ContributorsTable.svelte";
  import AnalyticsConversionRates from "$lib/containers/homeDashboard/DashboardCharts/AnalyticsConversionRates.svelte";
  import OsBreakdown from "$lib/containers/homeDashboard/DashboardCharts/OSBreakdown.svelte";
  import Sales from "$lib/containers/homeDashboard/DashboardCharts/Sales.svelte";
  import SalesByPlan from "$lib/containers/homeDashboard/DashboardCharts/SalesByPlan.svelte";
  import DashboardSelect from "$lib/containers/homeDashboard/DashboardSelect/DashboardSelect.svelte";
  import HomeCard from "$lib/containers/homeDashboard/HomeCards/HomeCard.svelte";
  import StatsCard from "$lib/containers/homeDashboard/HomeCards/StatsCard.svelte";
  import {
    DownloadsStat,
    UserStat,
    VisitStats,
  } from "$lib/containers/homeDashboard/Stats";

  import { t } from "$lib/locales/i18n";
  import { onDestroy } from "svelte";
  import { fly } from "svelte/transition";

  onDestroy(() => console.log("destroyed"));
</script>

<div
  class="space-y-4 m-4 p-4 sm:grid sm:space-y-0 sm:grid-cols-1 sm:gap-4 xl:grid-cols-3 xl:gap-8"
>
  <div
    class="card sm:col-span-1"
    transition:fly|local={{ y: -200, duration: 500 }}
  >
    <HomeCard />
  </div>
  <div
    class="card sm:col-span-1"
    transition:fly|local={{ x: -200, duration: 500 }}
  >
    <DashboardSelect />
  </div>
  <div class="card sm:col-span-1 h-52"><Awards /></div>
  <div
    class="card sm:col-span-1"
    transition:fly|local={{ x: 200, duration: 500 }}
  >
    <UserStat />
  </div>
  <div
    class="card sm:col-span-1"
    transition:fly|local={{ y: 200, duration: 500 }}
  >
    <VisitStats />
  </div>
  <div
    class="card sm:col-span-1"
    transition:fly|local={{ y: -200, duration: 500 }}
  >
    <DownloadsStat />
  </div>
  <div
    class="card sm:col-span-1 xl:col-span-2"
    transition:fly|local={{ x: -200, duration: 500 }}
  >
    <Sales />
  </div>
  <div
    class="card sm:col-span-1"
    transition:fly|local={{ x: 200, duration: 500 }}
  >
    <SalesByPlan />
  </div>
  <div
    class="card sm:col-span-1"
    transition:fly|local={{ x: -200, duration: 500 }}
  >
    <OsBreakdown />
  </div>
  <div
    class="card sm:col-span-1 xl:col-span-2"
    transition:fly|local={{ y: 200, duration: 500 }}
  >
    <ContributorsTable />
  </div>
  <div
    class="sm:col-span-1 sm:flex sm:flex-col sm:gap-4"
    transition:fly|local={{ y: -200, duration: 500 }}
  >
    <StatsCard
      title="32,251"
      subTitle={$t("homepage.conversersions.card")}
      percentage={75}
      color="primary"
    />
    <StatsCard
      title="54,635"
      subTitle={$t("homepage.applications.card")}
      percentage={43}
      color="secondary"
    />
  </div>
  <div
    class="card sm:col-span-1 xl:col-span-2"
    transition:fly|local={{ y: -200, duration: 500 }}
  >
    <AnalyticsConversionRates />
  </div>
</div>
