<template>
  <footer
    class="border-t border-[var(--nav-border)] bg-[var(--nav-bg)] py-12 sm:py-16"
  >
    <div class="mx-auto max-w-7xl px-5 sm:px-6 lg:px-8">
      <div
        class="grid gap-10 lg:grid-cols-[1.4fr_2fr]"
      >
        <div>
          <a
        href="#home"
        class="group shrink-0 text-xl font-bold tracking-[-0.04em] text-[var(--nav-text)] transition-opacity duration-300 hover:opacity-70"
        @click="setActiveLink('Home')"
      >
        <span>Studio</span><span class="text-[var(--nav-muted)]">.</span>
      </a>

          <p
            class="mt-4 max-w-sm text-sm leading-6 text-[var(--nav-muted)]"
          >
            A focused workspace for modern teams to organize work,
            collaborate, and move projects forward.
          </p>

          <div class="mt-6 flex items-center gap-2">
            <a
              v-for="social in socialLinks"
              :key="social.label"
              href="#"
              :aria-label="social.label"
              class="flex h-9 w-9 items-center justify-center rounded-full border border-[var(--nav-border)] text-[var(--nav-muted)] transition-all duration-300 hover:-translate-y-0.5 hover:bg-[var(--nav-hover)] hover:text-[var(--nav-text)]"
            >
              <component
                :is="social.icon"
                class="h-4 w-4"
                aria-hidden="true"
              />
            </a>
          </div>
        </div>

        <div
          class="grid grid-cols-2 gap-8 sm:grid-cols-4"
        >
          <div
            v-for="column in footerColumns"
            :key="column.title"
          >
            <h3
              class="text-xs font-semibold uppercase tracking-[0.16em] text-[var(--nav-text)]"
            >
              {{ column.title }}
            </h3>

            <ul class="mt-4 space-y-3">
              <li
                v-for="link in column.links"
                :key="link"
              >
                <a
                  href="#"
                  class="text-sm text-[var(--nav-muted)] transition-colors duration-300 hover:text-[var(--nav-text)]"
                >
                  {{ link }}
                </a>
              </li>
            </ul>
          </div>
        </div>
      </div>

      <div
        class="mt-12 flex flex-col gap-4 border-t border-[var(--nav-border)] pt-6 sm:flex-row sm:items-center sm:justify-between"
      >
        <p
          class="text-xs text-[var(--nav-muted)]"
        >
          © 2026 Flow. All rights reserved.
        </p>

        <p
          class="text-xs text-[var(--nav-muted)]"
        >
          Built for teams that move fast.
        </p>
      </div>
    </div>
  </footer>
</template>

<script>
import {
  Github,
  LineChart,
  Send,
} from 'lucide-vue-next';

export default {
  name: 'Footer',

  components: {
    Github,
    LineChart,
    Send,
  },

  data() {
    return {
      socialLinks: [
        {
          label: 'GitHub',
          icon: Github,
        },
        {
          label: 'Send email',
          icon: Send,
        },
        {
          label: 'Activity',
          icon: LineChart,
        },
      ],

      footerColumns: [
        {
          title: 'Product',
          links: [
            'Features',
            'Pricing',
            'Changelog',
            'Roadmap',
          ],
        },
        {
          title: 'Company',
          links: [
            'About',
            'Careers',
            'Contact',
            'Press',
          ],
        },
        {
          title: 'Resources',
          links: [
            'Documentation',
            'Help center',
            'Guides',
            'Community',
          ],
        },
        {
          title: 'Legal',
          links: [
            'Privacy',
            'Terms',
            'Security',
            'Cookies',
          ],
        },
      ],
    };
  },
};
</script>