<template>
  <header
    className="pointer-events-none relative z-50 flex flex-none flex-col"
    :style="{
      height: 'var(--header-height)',
      marginBottom: 'var(--header-mb)',
    }"
  >
    <div class="top-0 order-last -mb-3 pt-3">
      <div class="top-[var(--header-top,theme(spacing.6))] w-full">
        <div class="relative flex gap-4">
          <div class="flex flex-1 justify-end md:justify-center">
            <nav class="hidden md:block">
              <ul
                class="flex rounded-full bg-white/90 px-3 text-sm font-medium text-zinc-800 shadow-lg shadow-zinc-800/5 ring-1 ring-zinc-900/5 backdrop-blur dark:bg-zinc-800/90 dark:text-zinc-200 dark:ring-white/10"
              >
                <NavItem href="/about">About</NavItem>
                <NavItem href="/articles">Articles</NavItem>
                <NavItem href="/projects">Projects</NavItem>
                <NavItem href="/speaking">Speaking</NavItem>
                <NavItem href="/uses">Uses</NavItem>
              </ul>
            </nav>
          </div>
        </div>
      </div>
    </div>
  </header>
  <div class="relative">
    <NuxtPage />
  </div>
</template>
