<template>
  <div class="no-scrollbar flex pb-0 pt-3 lg:block lg:pb-3">
    <router-link v-slot="{ isExactActive }" :to="{ name: 'profileActivity' }">
      <BaseSidebarNavigationItem :is-active="isExactActive">
        {{ $t('profile.activity.header') }}
      </BaseSidebarNavigationItem>
    </router-link>
    <router-link v-slot="{ isExactActive }" :to="{ name: 'profileAbout' }">
      <BaseSidebarNavigationItem :is-active="isExactActive">
        {{ $t('profile.about.header') }}
      </BaseSidebarNavigationItem>
    </router-link>
  </div>
</template>
