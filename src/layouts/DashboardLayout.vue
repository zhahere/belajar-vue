<script setup lang="ts">
import { RouterView, RouterLink } from 'vue-router'
</script>

<template>
  <div class="dashboard-layout">
    <!-- Sidebar -->
    <aside class="dashboard-rail">
      <div class="rail-brand">
        <RouterLink to="/">Gatherly Organizer</RouterLink>
      </div>

      <nav class="rail-nav">
        <RouterLink
          to="/dashboard"
          class="rail-link"
          active-class="active"
          exact-active-class="active"
        >
          Overview
        </RouterLink>

        <a href="#" class="rail-link">My Events</a>
        <a href="#" class="rail-link">Attendees</a>
        <a href="#" class="rail-link">QR Check-in</a>
      </nav>

      <div class="rail-footer">
        <RouterLink to="/" class="rail-link"> &larr; Back to Public </RouterLink>
      </div>
    </aside>

    <!-- Konten dashboard -->
    <main class="dashboard-pane">
      <header class="pane-header">
        <h1>Dashboard</h1>
        <div class="user-profile">Admin</div>
      </header>

      <div class="pane-content">
        <RouterView />
      </div>
    </main>
  </div>
</template>

<style scoped>
.dashboard-layout {
  display: flex;
  width: 100%;
  height: 100vh;
  overflow: hidden;
  background-color: var(--bg-gray);
}

.dashboard-rail {
  flex: 0 0 250px;
  width: 250px;
  background-color: #1c1948;
  color: white;
  display: flex;
  flex-direction: column;
}

.rail-brand {
  padding: 16px;
  font-size: 1rem;
  font-weight: 700;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.rail-brand a {
  color: white;
  text-decoration: none;
}

.rail-nav {
  flex: 1;
  padding: 12px 0;
  display: flex;
  flex-direction: column;
}

.rail-link {
  display: block;
  padding: 10px 16px;
  color: #aaa;
  text-decoration: none;
  font-size: 0.9rem;
  font-weight: 500;
  border-left: 4px solid transparent;
  transition:
    background-color 0.2s,
    color 0.2s;
}

.rail-link:hover,
.rail-link.active {
  background-color: rgba(255, 255, 255, 0.08);
  color: white;
  border-left-color: var(--primary);
}

.rail-footer {
  padding: 12px 0;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
}

.dashboard-pane {
  flex: 1;
  min-width: 0;
  display: flex;
  flex-direction: column;
  overflow-y: auto;
}

.pane-header {
  flex-shrink: 0;
  background: white;
  padding: 16px 24px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid var(--border-color);
}

.pane-header h1 {
  font-size: 1.25rem;
  margin: 0;
}

.user-profile {
  font-size: 0.85rem;
}

.pane-content {
  flex: 1;
  padding: 24px;
  overflow-x: auto;
}

@media (max-width: 768px) {
  .dashboard-rail {
    flex-basis: 160px;
    width: 160px;
  }

  .pane-content {
    padding: 16px;
  }
}
</style>
