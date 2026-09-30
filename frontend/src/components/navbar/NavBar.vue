<script setup lang="ts">
import { RouterView } from 'vue-router'
import FriendIcon from "@/components/navbar/icons/FriendIcon.vue";
import CreateIcon from "@/components/navbar/icons/CreateIcon.vue";
import HomepageIcon from "@/components/navbar/icons/HomepageIcon.vue";
</script>

<template>
  <div class="drawer lg:drawer-open">
    <input id="my-drawer-4" type="checkbox" class="drawer-toggle inline" />
    <div class="drawer-content">
      <!-- Navbar -->
      <nav class="navbar w-full bg-base-100 shadow-lg" >
        <div class="navbar-start">
          <label for="my-drawer-4" aria-label="open sidebar" class="btn btn-square btn-ghost drawer-button">
            <!-- Sidebar toggle icon -->
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" stroke-linejoin="round" stroke-linecap="round" stroke-width="2" fill="none" stroke="currentColor" class="my-1.5 inline-block size-4"><path d="M4 4m0 2a2 2 0 0 1 2 -2h12a2 2 0 0 1 2 2v12a2 2 0 0 1 -2 2h-12a2 2 0 0 1 -2 -2z"></path><path d="M9 4v16"></path><path d="M14 10l2 2l-2 2"></path></svg>
          </label>
          <div class="px-2 font-bold">Navbar Title</div>
        </div>
        <div class="navbar-center w-4/5 max-w-180 felx justify-center">
          <div class="join w-4/5 flex justify-center">
            <input class="input join-item rounded-l-full w-4/5" placeholder="搜索内容" />
            <button class="btn join-item rounded-r-full">搜索</button>
          </div>
        </div>

        <div class="navbar-end">
          <RouterLink :to="{name: 'login-index'}" class="btn btn-ghost text-lg">登录</RouterLink>
        </div>

      </nav>
      <!-- Page content here -->
      <slot></slot>
    </div>

    <div class="drawer-side is-drawer-close:overflow-visible">
      <label for="my-drawer-4" aria-label="close sidebar" class="drawer-overlay"></label>
      <div class="flex min-h-full flex-col items-start bg-base-200 is-drawer-close:w-14 is-drawer-open:w-64">
        <!-- Sidebar content here -->
        <ul class="menu w-full grow">
          <!-- List item -->
          <li>
            <RouterLink :to="{name: 'homepage-index'}" class="is-drawer-close:tooltip is-drawer-close:tooltip-right" data-tip="Homepage">
              <!-- Home icon -->
              <HomepageIcon/>
              <span class="is-drawer-close:hidden">首页</span>
            </RouterLink>
          </li>

          <!-- List item -->
          <li>
            <RouterLink :to="{name: 'friend-index'}" class="is-drawer-close:tooltip is-drawer-close:tooltip-right" data-tip="Settings">
              <!-- Settings icon -->
              <FriendIcon/>
              <span class="is-drawer-close:hidden">好友</span>
            </RouterLink>
          </li>

          <!-- List item -->
          <li>
            <RouterLink :to="{name: 'create-index'}" class="is-drawer-close:tooltip is-drawer-close:tooltip-right" data-tip="Settings">
              <!-- Settings icon -->
              <CreateIcon/>
              <span class="is-drawer-close:hidden">创作</span>
            </RouterLink>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>