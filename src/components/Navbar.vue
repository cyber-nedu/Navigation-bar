<template>
  <header
    :class="[
      'fixed inset-x-0 z-50 transition-all duration-500 bg-[var(--nav-text)]/5',
    ]"
  >
    <nav
      class="mx-auto flex h-20 max-w-7xl items-center justify-between px-5 sm:px-6 lg:px-8"
      aria-label="Main navigation"
    >
      <a
        href="#home"
        class="group shrink-0 text-xl font-bold tracking-[-0.04em] text-[var(--nav-text)] transition-opacity duration-300 hover:opacity-70"
        @click="setActiveLink('Home')"
      >
        <span>Studio</span><span class="text-[var(--nav-muted)]">.</span>
      </a>

      <div class="hidden items-center md:flex">
        <div
          class="flex items-center gap-1 rounded-full border border-[var(--nav-border)] bg-[var(--nav-surface)] p-1"
        >
          <template v-for="item in navLinks" :key="item.title">
            <div v-if="item.dropdown" class="relative">
              <button
                type="button"
                :aria-expanded="openDropdown"
                class="group relative flex items-center gap-1.5 rounded-full px-4 py-2 text-sm font-medium text-[var(--nav-muted)] transition-all duration-300 hover:text-[var(--nav-text)] focus:outline-none focus-visible:ring-2 focus-visible:ring-[var(--nav-text)] focus-visible:ring-offset-2 focus-visible:ring-offset-[var(--nav-bg)]"
                @click="toggleDropdown"
              >
                {{ item.title }}

                <ChevronDown
                  class="h-3.5 w-3.5 transition-transform duration-300"
                  :class="{ 'rotate-180': openDropdown }"
                  aria-hidden="true"
                />

                <span
                  class="absolute inset-x-4 bottom-1 h-px origin-left scale-x-0 bg-[var(--nav-text)] transition-transform duration-300 ease-out group-hover:scale-x-100"
                />
              </button>

              <Transition
                enter-active-class="transition duration-200 ease-out"
                enter-from-class="translate-y-2 opacity-0"
                enter-to-class="translate-y-0 opacity-100"
                leave-active-class="transition duration-150 ease-in"
                leave-from-class="translate-y-0 opacity-100"
                leave-to-class="translate-y-2 opacity-0"
              >
                <div
                  v-if="openDropdown"
                  class="absolute left-1/2 top-[calc(100%+14px)] w-56 -translate-x-1/2 overflow-hidden rounded-2xl border border-[var(--nav-border)] bg-[var(--nav-surface-solid)] p-2 shadow-[0_20px_50px_rgba(0,0,0,0.12)]"
                >
                  <a
                    v-for="dropdownItem in dropdownItems"
                    :key="dropdownItem.title"
                    :href="dropdownItem.link"
                    class="group flex items-center justify-between rounded-xl px-3 py-3 text-sm text-[var(--nav-muted)] transition-colors duration-200 hover:bg-[var(--nav-hover)] hover:text-[var(--nav-text)]"
                    @click="closeDropdown"
                  >
                    <span>{{ dropdownItem.title }}</span>

                    <ArrowRight
                      class="h-4 w-4 -translate-x-1 opacity-0 transition-all duration-200 group-hover:translate-x-0 group-hover:opacity-100"
                      aria-hidden="true"
                    />
                  </a>
                </div>
              </Transition>
            </div>

            <a
              v-else
              :href="item.link"
              :class="[
                'group relative rounded-full px-4 py-2 text-sm font-medium transition-all duration-300 focus:outline-none focus-visible:ring-2 focus-visible:ring-[var(--nav-text)] focus-visible:ring-offset-2 focus-visible:ring-offset-[var(--nav-bg)]',
                activeLink === item.title
                  ? 'text-[var(--nav-text)]'
                  : 'text-[var(--nav-muted)] hover:text-[var(--nav-text)]',
              ]"
              @click="setActiveLink(item.title)"
            >
              {{ item.title }}

              <span
                :class="[
                  'absolute inset-x-4 bottom-1 h-px origin-left bg-[var(--nav-text)] transition-transform duration-300 ease-out',
                  activeLink === item.title
                    ? 'scale-x-100'
                    : 'scale-x-0 group-hover:scale-x-100',
                ]"
              />
            </a>
          </template>
        </div>
      </div>

      <div class="hidden items-center gap-3 md:flex">
        <button
          type="button"
          class="flex h-10 w-10 items-center justify-center rounded-full border border-[var(--nav-border)] text-[var(--nav-muted)] transition-all duration-300 hover:bg-[var(--nav-hover)] hover:text-[var(--nav-text)] focus:outline-none focus-visible:ring-2 focus-visible:ring-[var(--nav-text)]"
          :aria-label="
            isDarkMode ? 'Switch to light mode' : 'Switch to dark mode'
          "
          @click="toggleTheme"
        >
          <Sun
            v-if="isDarkMode"
            class="h-4 w-4"
            aria-hidden="true"
          />

          <Moon
            v-else
            class="h-4 w-4"
            aria-hidden="true"
          />
        </button>

        <a
          href="#contact"
          class="group relative overflow-hidden rounded-full bg-[var(--nav-text)] px-5 py-2.5 text-sm font-semibold text-[var(--nav-bg)] transition-all duration-300 hover:bg-[var(--nav-bg)] hover:text-[var(--nav-text)] hover:ring-1 hover:ring-[var(--nav-text)] focus:outline-none focus-visible:ring-2 focus-visible:ring-[var(--nav-text)]"
          @click="setActiveLink('Contact')"
        >
          <span class="relative z-10">Let's talk</span>
        </a>
      </div>

      <div class="flex items-center gap-2 md:hidden">
        <button
          type="button"
          class="flex h-10 w-10 items-center justify-center rounded-full border border-[var(--nav-border)] text-[var(--nav-muted)] transition-colors duration-300 hover:bg-[var(--nav-hover)] hover:text-[var(--nav-text)] focus:outline-none focus-visible:ring-2 focus-visible:ring-[var(--nav-text)]"
          :aria-label="
            isDarkMode ? 'Switch to light mode' : 'Switch to dark mode'
          "
          @click="toggleTheme"
        >
          <Sun
            v-if="isDarkMode"
            class="h-4 w-4"
            aria-hidden="true"
          />

          <Moon
            v-else
            class="h-4 w-4"
            aria-hidden="true"
          />
        </button>

        <button
          type="button"
          class="relative flex h-10 w-10 items-center justify-center rounded-full border border-[var(--nav-border)] text-[var(--nav-text)] transition-colors duration-300 hover:bg-[var(--nav-hover)] focus:outline-none focus-visible:ring-2 focus-visible:ring-[var(--nav-text)]"
          :aria-expanded="mobileMenuOpen"
          aria-controls="mobile-navigation"
          aria-label="Toggle navigation menu"
          @click="toggleMobileMenu"
        >
          <Menu
            v-if="!mobileMenuOpen"
            class="h-5 w-5"
            aria-hidden="true"
          />

          <X
            v-else
            class="h-5 w-5"
            aria-hidden="true"
          />
        </button>
      </div>
    </nav>

    <Transition
      enter-active-class="transition-opacity duration-300"
      enter-from-class="opacity-0"
      enter-to-class="opacity-100"
      leave-active-class="transition-opacity duration-200"
      leave-from-class="opacity-100"
      leave-to-class="opacity-0"
    >
      <div
        v-if="mobileMenuOpen"
        class="fixed inset-0 top-20 z-40 bg-black/40 backdrop-blur-sm md:hidden"
        aria-hidden="true"
        @click="closeMobileMenu"
      />
    </Transition>

    <Transition
      enter-active-class="transition-transform duration-500 ease-[cubic-bezier(0.22,1,0.36,1)]"
      enter-from-class="translate-x-full"
      enter-to-class="translate-x-0"
      leave-active-class="transition-transform duration-400 ease-in"
      leave-from-class="translate-x-0"
      leave-to-class="translate-x-full"
    >
      <aside
        v-if="mobileMenuOpen"
        id="mobile-navigation"
        class="fixed right-0 top-20 z-50 flex h-[calc(100dvh-5rem)] w-[min(88%,380px)] flex-col border-l border-[var(--nav-border)] bg-[var(--nav-surface-solid)] p-6 shadow-[-20px_0_60px_rgba(0,0,0,0.15)] md:hidden"
        aria-label="Mobile navigation"
      >
        <div class="flex flex-1 flex-col">
          <p
            class="mb-6 text-xs font-medium uppercase tracking-[0.2em] text-[var(--nav-muted)]"
          >
            Navigation
          </p>

          <div class="flex flex-col">
            <template v-for="(item, index) in navLinks" :key="item.title">
              <div v-if="item.dropdown">
                <button
                  type="button"
                  class="mobile-link flex w-full items-center justify-between border-b border-[var(--nav-border)] py-4 text-left text-2xl font-medium tracking-tight text-[var(--nav-text)]"
                  :style="{ '--delay': `${index * 70}ms` }"
                  @click="toggleMobileDropdown"
                >
                  {{ item.title }}

                  <ChevronDown
                    class="h-5 w-5 transition-transform duration-300"
                    :class="{ 'rotate-180': mobileDropdownOpen }"
                    aria-hidden="true"
                  />
                </button>

                <div
                  v-if="mobileDropdownOpen"
                  class="overflow-hidden border-b border-[var(--nav-border)] pl-4"
                >
                  <a
                    v-for="dropdownItem in dropdownItems"
                    :key="dropdownItem.title"
                    :href="dropdownItem.link"
                    class="block border-b border-[var(--nav-border)] py-3 text-sm text-[var(--nav-muted)] last:border-b-0"
                    @click="closeMobileMenu"
                  >
                    {{ dropdownItem.title }}
                  </a>
                </div>
              </div>

              <a
                v-else
                :href="item.link"
                :class="[
                  'mobile-link border-b border-[var(--nav-border)] py-4 text-2xl font-medium tracking-tight transition-colors duration-300',
                  activeLink === item.title
                    ? 'text-[var(--nav-text)]'
                    : 'text-[var(--nav-muted)] hover:text-[var(--nav-text)]',
                ]"
                :style="{ '--delay': `${index * 70}ms` }"
                @click="handleMobileLink(item.title)"
              >
                <span class="flex items-center justify-between">
                  {{ item.title }}

                  <ArrowRight
                    class="h-5 w-5 opacity-0 transition-all duration-300"
                    :class="
                      activeLink === item.title
                        ? 'translate-x-0 opacity-100'
                        : '-translate-x-2'
                    "
                    aria-hidden="true"
                  />
                </span>
              </a>
            </template>
          </div>
        </div>

        <a
          href="#contact"
          class="mobile-cta rounded-full bg-[var(--nav-text)] px-6 py-4 text-center text-sm font-semibold text-[var(--nav-bg)] transition-all duration-300 hover:bg-[var(--nav-bg)] hover:text-[var(--nav-text)] hover:ring-1 hover:ring-[var(--nav-text)]"
          @click="handleMobileLink('Contact')"
        >
          Let's talk
        </a>
      </aside>
    </Transition>
  </header>
</template>

<script>
import {
  ArrowRight,
  ChevronDown,
  Menu,
  Moon,
  Sun,
  X,
} from 'lucide-vue-next';

export default {
  name: 'Navbar',

  components: {
    ArrowRight,
    ChevronDown,
    Menu,
    Moon,
    Sun,
    X,
  },

  data() {
    return {
      navLinks: [
        {
          title: 'Home',
          link: '#home',
        },
        {
          title: 'About',
          link: '#about',
        },
        {
          title: 'Services',
          dropdown: true,
        },
        {
          title: 'Contact',
          link: '#contact',
        },
      ],

      dropdownItems: [
        {
          title: 'Web Development',
          link: '#web-development',
        },
        {
          title: 'UI Development',
          link: '#ui-development',
        },
        {
          title: 'Frontend Solutions',
          link: '#frontend-solutions',
        },
      ],

      activeLink: 'Home',
      isScrolled: false,
      isVisible: true,
      lastScrollY: 0,
      mobileMenuOpen: false,
      mobileDropdownOpen: false,
      openDropdown: false,
      isDarkMode: false,
    };
  },

  mounted() {
    this.lastScrollY = window.scrollY;

    window.addEventListener('scroll', this.handleScroll, {
      passive: true,
    });

    document.addEventListener('click', this.handleOutsideClick);

    const savedTheme = localStorage.getItem('navbar-theme');

    if (savedTheme === 'dark') {
      this.isDarkMode = true;
      document.documentElement.classList.add('dark');
    }
  },

  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll);
    document.removeEventListener('click', this.handleOutsideClick);
  },

  methods: {
    handleScroll() {
      const currentScrollY = window.scrollY;

      this.isScrolled = currentScrollY > 20;

      if (currentScrollY <= 20) {
        this.isVisible = true;
      } else if (currentScrollY > this.lastScrollY && currentScrollY > 100) {
        this.isVisible = false;
        this.openDropdown = false;
      } else if (currentScrollY < this.lastScrollY) {
        this.isVisible = true;
      }

      this.lastScrollY = currentScrollY;
    },

    setActiveLink(title) {
      this.activeLink = title;
      this.openDropdown = false;
    },

    toggleDropdown() {
      this.openDropdown = !this.openDropdown;
    },

    closeDropdown() {
      this.openDropdown = false;
    },

    handleOutsideClick(event) {
      if (!event.target.closest('.relative')) {
        this.openDropdown = false;
      }
    },

    toggleMobileMenu() {
      this.mobileMenuOpen = !this.mobileMenuOpen;

      if (!this.mobileMenuOpen) {
        this.mobileDropdownOpen = false;
      }

      document.body.style.overflow = this.mobileMenuOpen ? 'hidden' : '';
    },

    closeMobileMenu() {
      this.mobileMenuOpen = false;
      this.mobileDropdownOpen = false;
      document.body.style.overflow = '';
    },

    toggleMobileDropdown() {
      this.mobileDropdownOpen = !this.mobileDropdownOpen;
    },

    handleMobileLink(title) {
      this.activeLink = title;
      this.closeMobileMenu();
    },

    toggleTheme() {
      this.isDarkMode = !this.isDarkMode;

      document.documentElement.classList.toggle(
        'dark',
        this.isDarkMode,
      );

      localStorage.setItem(
        'navbar-theme',
        this.isDarkMode ? 'dark' : 'light',
      );
    },
  },
};
</script>

<style scoped>
.mobile-link {
  animation: mobile-link-enter 500ms cubic-bezier(0.22, 1, 0.36, 1) both;
  animation-delay: var(--delay);
}

.mobile-cta {
  animation: mobile-cta-enter 600ms cubic-bezier(0.22, 1, 0.36, 1) 250ms
    both;
}

@keyframes mobile-link-enter {
  from {
    opacity: 0;
    transform: translateX(24px);
  }

  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes mobile-cta-enter {
  from {
    opacity: 0;
    transform: translateY(12px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>