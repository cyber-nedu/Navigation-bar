<template>
  <main>
    <section
      id="home"
      class="relative overflow-hidden border-b border-[var(--nav-border)] pt-32 sm:pt-36 lg:pt-40"
    >
      <div
        class="pointer-events-none absolute left-1/2 top-20 h-[520px] w-[520px] -translate-x-1/2 rounded-full bg-[var(--nav-text)]/[0.035] blur-3xl"
      />

      <div
        class="relative mx-auto max-w-7xl px-5 pb-20 text-center sm:px-6 sm:pb-24 lg:px-8 lg:pb-28"
      >
        <div
          class="reveal mx-auto mb-7 inline-flex items-center gap-2 rounded-full border border-[var(--nav-border)] bg-[var(--nav-surface)] px-3.5 py-1.5 text-xs font-medium text-[var(--nav-muted)]"
        >
          <span class="h-1.5 w-1.5 rounded-full bg-[var(--nav-text)]" />
          Built for teams that move fast
        </div>

        <h1
          class="reveal mx-auto max-w-5xl text-4xl font-semibold tracking-[-0.055em] text-[var(--nav-text)] sm:text-5xl md:text-6xl lg:text-7xl"
        >
          Everything your team needs to
          <span class="text-[var(--nav-muted)]">move work forward.</span>
        </h1>

        <p
          class="reveal mx-auto mt-6 max-w-2xl text-base leading-7 text-[var(--nav-muted)] sm:text-lg sm:leading-8"
        >
          Flow gives modern teams one place to organize projects, manage tasks,
          collaborate in real time, and turn plans into finished work.
        </p>

        <div
          class="reveal mt-9 flex flex-col items-center justify-center gap-3 sm:flex-row"
        >
          <a
            href="#pricing"
            class="inline-flex h-12 items-center justify-center rounded-full bg-[var(--nav-text)] px-7 text-sm font-semibold text-[var(--nav-bg)] transition-all duration-300 hover:-translate-y-0.5 hover:shadow-xl focus:outline-none focus-visible:ring-2 focus-visible:ring-[var(--nav-text)] focus-visible:ring-offset-2"
          >
            Get started
          </a>

          <a
            href="#product"
            class="inline-flex h-12 items-center justify-center rounded-full border border-[var(--nav-border)] bg-[var(--nav-surface)] px-7 text-sm font-semibold text-[var(--nav-text)] transition-all duration-300 hover:-translate-y-0.5 hover:bg-[var(--nav-hover)] focus:outline-none focus-visible:ring-2 focus-visible:ring-[var(--nav-text)] focus-visible:ring-offset-2"
          >
            Explore Flow
          </a>
        </div>

        <p
          class="reveal mt-7 text-xs font-medium uppercase tracking-[0.18em] text-[var(--nav-muted)]"
        >
          Trusted by 10,000+ teams
        </p>
      </div>
    </section>

    <section
      id="product"
      class="overflow-hidden border-b border-[var(--nav-border)] py-20 sm:py-24 lg:py-28"
    >
      <div class="mx-auto max-w-7xl px-5 sm:px-6 lg:px-8">
        <div class="reveal mx-auto max-w-2xl text-center">
          <p
            class="text-xs font-semibold uppercase tracking-[0.2em] text-[var(--nav-muted)]"
          >
            One workspace
          </p>

          <h2
            class="mt-4 text-3xl font-semibold tracking-[-0.04em] text-[var(--nav-text)] sm:text-4xl"
          >
            Your entire workflow, in one place.
          </h2>

          <p class="mt-4 text-base leading-7 text-[var(--nav-muted)]">
            From the first idea to the final release, Flow keeps everyone
            aligned without getting in the way.
          </p>
        </div>

        <div
          class="reveal dashboard-preview mt-12 overflow-hidden rounded-2xl border border-[var(--nav-border)] bg-[var(--nav-surface-solid)] shadow-[0_30px_80px_rgba(0,0,0,0.12)]"
        >
          <div
            class="flex h-12 items-center justify-between border-b border-[var(--nav-border)] px-4 sm:px-5"
          >
            <div class="flex items-center gap-2">
              <div class="flex gap-1.5">
                <span
                  class="h-2.5 w-2.5 rounded-full bg-[var(--nav-border)]"
                />
                <span
                  class="h-2.5 w-2.5 rounded-full bg-[var(--nav-border)]"
                />
                <span
                  class="h-2.5 w-2.5 rounded-full bg-[var(--nav-border)]"
                />
              </div>

              <span
                class="ml-3 hidden text-xs font-medium text-[var(--nav-muted)] sm:block"
              >
                Flow / Product Launch
              </span>
            </div>

            <div class="flex items-center gap-2">
              <div
                class="hidden h-7 w-20 rounded-md border border-[var(--nav-border)] sm:block"
              />

              <div
                class="h-7 w-7 rounded-full bg-[var(--nav-text)] text-center text-[10px] font-semibold leading-7 text-[var(--nav-bg)]"
              >
                JD
              </div>
            </div>
          </div>

          <div class="flex min-h-[440px]">
            <aside
              class="hidden w-48 shrink-0 border-r border-[var(--nav-border)] p-4 md:block"
            >
              <div
                class="mb-6 flex items-center gap-2 text-sm font-semibold text-[var(--nav-text)]"
              >
                <span
                  class="flex h-6 w-6 items-center justify-center rounded-md bg-[var(--nav-text)] text-[10px] text-[var(--nav-bg)]"
                >
                  F
                </span>
                Flow
              </div>

              <div class="space-y-1">
                <div
                  v-for="item in dashboardSidebar"
                  :key="item"
                  class="rounded-md px-3 py-2 text-xs"
                  :class="
                    item === 'Overview'
                      ? 'bg-[var(--nav-hover)] font-medium text-[var(--nav-text)]'
                      : 'text-[var(--nav-muted)]'
                  "
                >
                  {{ item }}
                </div>
              </div>

              <div class="mt-8">
                <p
                  class="px-3 text-[10px] font-semibold uppercase tracking-[0.16em] text-[var(--nav-muted)]"
                >
                  Projects
                </p>

                <div class="mt-2 space-y-1">
                  <div
                    v-for="project in dashboardProjects"
                    :key="project"
                    class="flex items-center gap-2 px-3 py-2 text-xs text-[var(--nav-muted)]"
                  >
                    <span
                      class="h-1.5 w-1.5 rounded-full bg-[var(--nav-text)]"
                    />
                    {{ project }}
                  </div>
                </div>
              </div>
            </aside>

            <div class="min-w-0 flex-1 p-4 sm:p-6">
              <div
                class="flex flex-col justify-between gap-4 border-b border-[var(--nav-border)] pb-5 sm:flex-row sm:items-center"
              >
                <div>
                  <p
                    class="text-[10px] font-semibold uppercase tracking-[0.16em] text-[var(--nav-muted)]"
                  >
                    Project overview
                  </p>

                  <h3
                    class="mt-1 text-lg font-semibold tracking-tight text-[var(--nav-text)]"
                  >
                    Product Launch
                  </h3>
                </div>

                <div class="flex -space-x-2">
                  <span
                    v-for="avatar in dashboardAvatars"
                    :key="avatar"
                    class="flex h-7 w-7 items-center justify-center rounded-full border-2 border-[var(--nav-surface-solid)] bg-[var(--nav-hover)] text-[9px] font-semibold text-[var(--nav-text)]"
                  >
                    {{ avatar }}
                  </span>
                </div>
              </div>

              <div class="mt-5 grid gap-4 sm:grid-cols-3">
                <div
                  v-for="stat in dashboardStats"
                  :key="stat.label"
                  class="rounded-xl border border-[var(--nav-border)] p-4"
                >
                  <p class="text-xs text-[var(--nav-muted)]">
                    {{ stat.label }}
                  </p>

                  <div class="mt-2 flex items-end justify-between gap-2">
                    <p
                      class="text-xl font-semibold tracking-tight text-[var(--nav-text)]"
                    >
                      {{ stat.value }}
                    </p>

                    <span
                      class="text-[10px] font-medium text-[var(--nav-muted)]"
                    >
                      {{ stat.detail }}
                    </span>
                  </div>
                </div>
              </div>

              <div class="mt-5 grid gap-4 lg:grid-cols-3">
                <div
                  v-for="column in kanbanColumns"
                  :key="column.title"
                  class="rounded-xl border border-[var(--nav-border)] bg-[var(--nav-bg)] p-3"
                >
                  <div class="mb-3 flex items-center justify-between">
                    <div class="flex items-center gap-2">
                      <span
                        class="h-1.5 w-1.5 rounded-full bg-[var(--nav-text)]"
                      />

                      <span
                        class="text-xs font-semibold text-[var(--nav-text)]"
                      >
                        {{ column.title }}
                      </span>
                    </div>

                    <span class="text-[10px] text-[var(--nav-muted)]">
                      {{ column.items.length }}
                    </span>
                  </div>

                  <div class="space-y-2">
                    <div
                      v-for="task in column.items"
                      :key="task.title"
                      class="rounded-lg border border-[var(--nav-border)] bg-[var(--nav-surface-solid)] p-3 transition-transform duration-300 hover:-translate-y-0.5"
                    >
                      <p
                        class="text-xs font-medium leading-5 text-[var(--nav-text)]"
                      >
                        {{ task.title }}
                      </p>

                      <div
                        v-if="task.progress"
                        class="mt-3 h-1 overflow-hidden rounded-full bg-[var(--nav-border)]"
                      >
                        <div
                          class="h-full rounded-full bg-[var(--nav-text)]"
                          :style="{ width: `${task.progress}%` }"
                        />
                      </div>

                      <div
                        class="mt-3 flex items-center justify-between text-[9px] text-[var(--nav-muted)]"
                      >
                        <span>{{ task.tag }}</span>
                        <span>{{ task.date }}</span>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section
      class="border-b border-[var(--nav-border)] py-10"
      aria-label="Companies using Flow"
    >
      <div class="mx-auto max-w-7xl px-5 sm:px-6 lg:px-8">
        <div
          class="flex flex-wrap items-center justify-center gap-x-10 gap-y-6 sm:justify-between"
        >
          <span
            v-for="logo in companyLogos"
            :key="logo"
            class="text-sm font-semibold tracking-tight text-[var(--nav-muted)] opacity-70"
          >
            {{ logo }}
          </span>
        </div>
      </div>
    </section>

    <section
      id="about"
      class="border-b border-[var(--nav-border)] py-20 sm:py-24 lg:py-28"
    >
      <div class="mx-auto max-w-7xl px-5 sm:px-6 lg:px-8">
        <div
          class="reveal flex flex-col justify-between gap-6 lg:flex-row lg:items-end"
        >
          <div class="max-w-2xl">
            <p
              class="text-xs font-semibold uppercase tracking-[0.2em] text-[var(--nav-muted)]"
            >
              Everything connected
            </p>

            <h2
              class="mt-4 text-3xl font-semibold tracking-[-0.04em] text-[var(--nav-text)] sm:text-4xl"
            >
              Work stays organized. Teams stay aligned.
            </h2>
          </div>

          <p class="max-w-md text-sm leading-6 text-[var(--nav-muted)]">
            Flow brings planning, execution, communication, and reporting
            together so your team can focus on meaningful work.
          </p>
        </div>

        <div
          class="mt-12 grid gap-px overflow-hidden rounded-2xl border border-[var(--nav-border)] bg-[var(--nav-border)] sm:grid-cols-2 lg:grid-cols-3"
        >
          <article
            v-for="feature in features"
            :key="feature.title"
            class="reveal group bg-[var(--nav-bg)] p-6 transition-colors duration-300 hover:bg-[var(--nav-surface)] sm:p-7"
          >
            <div
              class="flex h-10 w-10 items-center justify-center rounded-xl border border-[var(--nav-border)] text-[var(--nav-text)] transition-transform duration-300 group-hover:-translate-y-1"
            >
              <component
                :is="feature.icon"
                class="h-5 w-5"
                aria-hidden="true"
              />
            </div>

            <h3 class="mt-6 text-base font-semibold text-[var(--nav-text)]">
              {{ feature.title }}
            </h3>

            <p class="mt-2 text-sm leading-6 text-[var(--nav-muted)]">
              {{ feature.description }}
            </p>
          </article>
        </div>
      </div>
    </section>

    <section
      id="services"
      class="border-b border-[var(--nav-border)] py-20 sm:py-24 lg:py-28"
    >
      <div class="mx-auto max-w-7xl px-5 sm:px-6 lg:px-8">
        <div class="reveal max-w-2xl">
          <p
            class="text-xs font-semibold uppercase tracking-[0.2em] text-[var(--nav-muted)]"
          >
            How it works
          </p>

          <h2
            class="mt-4 text-3xl font-semibold tracking-[-0.04em] text-[var(--nav-text)] sm:text-4xl"
          >
            From idea to shipped.
          </h2>

          <p class="mt-4 text-base leading-7 text-[var(--nav-muted)]">
            A simple workflow designed to keep everyone moving in the same
            direction.
          </p>
        </div>

        <div class="relative mt-14 grid gap-10 lg:grid-cols-3 lg:gap-8">
          <div
            class="absolute left-[16.66%] right-[16.66%] top-6 hidden h-px bg-[var(--nav-border)] lg:block"
          />

          <article
            v-for="step in steps"
            :key="step.number"
            class="reveal relative"
          >
            <div
              class="relative flex h-12 w-12 items-center justify-center rounded-full border border-[var(--nav-border)] bg-[var(--nav-bg)] text-sm font-semibold text-[var(--nav-text)]"
            >
              {{ step.number }}
            </div>

            <h3
              class="mt-6 text-lg font-semibold tracking-tight text-[var(--nav-text)]"
            >
              {{ step.title }}
            </h3>

            <p
              class="mt-2 max-w-sm text-sm leading-6 text-[var(--nav-muted)]"
            >
              {{ step.description }}
            </p>
          </article>
        </div>
      </div>
    </section>

    <section
      class="border-b border-[var(--nav-border)] py-20 sm:py-24 lg:py-28"
    >
      <div class="mx-auto max-w-7xl px-5 sm:px-6 lg:px-8">
        <div
          class="grid items-center gap-12 lg:grid-cols-[0.9fr_1.1fr] lg:gap-20"
        >
          <div class="reveal">
            <p
              class="text-xs font-semibold uppercase tracking-[0.2em] text-[var(--nav-muted)]"
            >
              Built for collaboration
            </p>

            <h2
              class="mt-4 text-3xl font-semibold tracking-[-0.04em] text-[var(--nav-text)] sm:text-4xl"
            >
              Less status meetings. More actual progress.
            </h2>

            <p
              class="mt-5 max-w-lg text-base leading-7 text-[var(--nav-muted)]"
            >
              Keep conversations attached to the work, share context instantly,
              and give everyone a clear view of what is happening.
            </p>

            <a
              href="#contact"
              class="mt-7 inline-flex items-center gap-2 text-sm font-semibold text-[var(--nav-text)] transition-opacity hover:opacity-60"
            >
              See how collaboration works
              <ArrowRight class="h-4 w-4" aria-hidden="true" />
            </a>
          </div>

          <div
            class="reveal rounded-2xl border border-[var(--nav-border)] bg-[var(--nav-surface)] p-4 shadow-[0_20px_60px_rgba(0,0,0,0.06)] sm:p-6"
          >
            <div
              class="rounded-xl border border-[var(--nav-border)] bg-[var(--nav-surface-solid)]"
            >
              <div
                class="flex items-center justify-between border-b border-[var(--nav-border)] px-4 py-4"
              >
                <div>
                  <p
                    class="text-[10px] font-semibold uppercase tracking-[0.16em] text-[var(--nav-muted)]"
                  >
                    Design review
                  </p>

                  <p
                    class="mt-1 text-sm font-semibold text-[var(--nav-text)]"
                  >
                    Landing page updates
                  </p>
                </div>

                <span
                  class="rounded-full border border-[var(--nav-border)] px-2.5 py-1 text-[10px] text-[var(--nav-muted)]"
                >
                  4 active
                </span>
              </div>

              <div class="space-y-5 p-4">
                <div
                  v-for="activity in activities"
                  :key="activity.name"
                  class="flex gap-3"
                >
                  <div
                    class="flex h-8 w-8 shrink-0 items-center justify-center rounded-full bg-[var(--nav-hover)] text-[10px] font-semibold text-[var(--nav-text)]"
                  >
                    {{ activity.initials }}
                  </div>

                  <div class="min-w-0 flex-1">
                    <p class="text-xs leading-5 text-[var(--nav-muted)]">
                      <span class="font-semibold text-[var(--nav-text)]">
                        {{ activity.name }}
                      </span>
                      {{ activity.action }}
                    </p>

                    <div
                      v-if="activity.comment"
                      class="mt-2 rounded-lg border border-[var(--nav-border)] bg-[var(--nav-bg)] p-3 text-xs leading-5 text-[var(--nav-muted)]"
                    >
                      {{ activity.comment }}
                    </div>

                    <p class="mt-1 text-[10px] text-[var(--nav-muted)]">
                      {{ activity.time }}
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section
      class="border-b border-[var(--nav-border)] py-20 sm:py-24 lg:py-28"
    >
      <div class="mx-auto max-w-7xl px-5 sm:px-6 lg:px-8">
        <div class="reveal text-center">
          <p
            class="text-xs font-semibold uppercase tracking-[0.2em] text-[var(--nav-muted)]"
          >
            Measurable progress
          </p>

          <h2
            class="mx-auto mt-4 max-w-2xl text-3xl font-semibold tracking-[-0.04em] text-[var(--nav-text)] sm:text-4xl"
          >
            Make better decisions with better visibility.
          </h2>
        </div>

        <div class="mt-14 grid gap-4 sm:grid-cols-3">
          <div
            v-for="stat in analyticsStats"
            :key="stat.label"
            class="reveal rounded-2xl border border-[var(--nav-border)] p-6 text-center sm:p-8"
          >
            <p
              class="counter text-4xl font-semibold tracking-[-0.05em] text-[var(--nav-text)] sm:text-5xl"
              :data-target="stat.target"
              :data-suffix="stat.suffix"
            >
              0{{ stat.suffix }}
            </p>

            <p class="mt-3 text-sm text-[var(--nav-muted)]">
              {{ stat.label }}
            </p>
          </div>
        </div>

        <div
          class="reveal mt-8 rounded-2xl border border-[var(--nav-border)] p-5 sm:p-7"
        >
          <div class="flex items-center justify-between">
            <div>
              <p class="text-sm font-semibold text-[var(--nav-text)]">
                Project velocity
              </p>

              <p class="mt-1 text-xs text-[var(--nav-muted)]">
                Completed work over the last 8 weeks
              </p>
            </div>

            <span class="text-xs font-medium text-[var(--nav-muted)]">
              +32%
            </span>
          </div>

          <div
            class="mt-8 flex h-48 items-end gap-2 border-b border-l border-[var(--nav-border)] px-3 pb-0 pt-5 sm:gap-4"
          >
            <div
              v-for="(height, index) in chartBars"
              :key="index"
              class="group relative flex h-full flex-1 items-end"
            >
              <div
                class="w-full rounded-t-md bg-[var(--nav-text)] opacity-80 transition-all duration-500 group-hover:opacity-100"
                :style="{ height: `${height}%` }"
              />

              <span
                class="absolute -bottom-6 left-1/2 -translate-x-1/2 text-[9px] text-[var(--nav-muted)]"
              >
                W{{ index + 1 }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section
      class="border-b border-[var(--nav-border)] py-20 sm:py-24 lg:py-28"
    >
      <div class="mx-auto max-w-7xl px-5 sm:px-6 lg:px-8">
        <div class="reveal text-center">
          <p
            class="text-xs font-semibold uppercase tracking-[0.2em] text-[var(--nav-muted)]"
          >
            Teams are saying
          </p>

          <h2
            class="mt-4 text-3xl font-semibold tracking-[-0.04em] text-[var(--nav-text)] sm:text-4xl"
          >
            Built to make work feel simpler.
          </h2>
        </div>

        <div class="mt-12 grid gap-4 lg:grid-cols-3">
          <article
            v-for="testimonial in testimonials"
            :key="testimonial.name"
            class="reveal rounded-2xl border border-[var(--nav-border)] p-6 transition-all duration-300 hover:-translate-y-1 hover:shadow-xl sm:p-7"
          >
            <div class="flex gap-1">
              <span
                v-for="star in 5"
                :key="star"
                class="text-xs text-[var(--nav-text)]"
              >
                ★
              </span>
            </div>

            <blockquote
              class="mt-6 text-sm leading-7 text-[var(--nav-muted)]"
            >
              “{{ testimonial.quote }}”
            </blockquote>

            <div class="mt-7 flex items-center gap-3">
              <div
                class="flex h-9 w-9 items-center justify-center rounded-full bg-[var(--nav-hover)] text-[10px] font-semibold text-[var(--nav-text)]"
              >
                {{ testimonial.initials }}
              </div>

              <div>
                <p class="text-xs font-semibold text-[var(--nav-text)]">
                  {{ testimonial.name }}
                </p>

                <p class="mt-0.5 text-[10px] text-[var(--nav-muted)]">
                  {{ testimonial.role }} · {{ testimonial.company }}
                </p>
              </div>
            </div>
          </article>
        </div>
      </div>
    </section>

    <section
      id="pricing"
      class="border-b border-[var(--nav-border)] py-20 sm:py-24 lg:py-28"
    >
      <div class="mx-auto max-w-7xl px-5 sm:px-6 lg:px-8">
        <div
          class="reveal flex flex-col items-start justify-between gap-6 sm:flex-row sm:items-end"
        >
          <div>
            <p
              class="text-xs font-semibold uppercase tracking-[0.2em] text-[var(--nav-muted)]"
            >
              Pricing
            </p>

            <h2
              class="mt-4 text-3xl font-semibold tracking-[-0.04em] text-[var(--nav-text)] sm:text-4xl"
            >
              Simple pricing that scales with you.
            </h2>
          </div>

          <div
            class="flex rounded-full border border-[var(--nav-border)] bg-[var(--nav-surface)] p-1"
          >
            <button
              type="button"
              :class="[
                'rounded-full px-4 py-2 text-xs font-semibold transition-all duration-300',
                billingCycle === 'monthly'
                  ? 'bg-[var(--nav-text)] text-[var(--nav-bg)]'
                  : 'text-[var(--nav-muted)]',
              ]"
              @click="billingCycle = 'monthly'"
            >
              Monthly
            </button>

            <button
              type="button"
              :class="[
                'rounded-full px-4 py-2 text-xs font-semibold transition-all duration-300',
                billingCycle === 'yearly'
                  ? 'bg-[var(--nav-text)] text-[var(--nav-bg)]'
                  : 'text-[var(--nav-muted)]',
              ]"
              @click="billingCycle = 'yearly'"
            >
              Yearly
              <span class="ml-1">−20%</span>
            </button>
          </div>
        </div>

        <div class="mt-12 grid gap-4 lg:grid-cols-3">
          <article
            v-for="plan in pricingPlans"
            :key="plan.name"
            class="reveal relative flex flex-col rounded-2xl border p-6 sm:p-7"
            :class="
              plan.popular
                ? 'border-[var(--nav-text)] shadow-[0_20px_60px_rgba(0,0,0,0.08)]'
                : 'border-[var(--nav-border)]'
            "
          >
            <div
              v-if="plan.popular"
              class="absolute right-5 top-5 rounded-full bg-[var(--nav-text)] px-2.5 py-1 text-[9px] font-semibold uppercase tracking-[0.12em] text-[var(--nav-bg)]"
            >
              Most Popular
            </div>

            <h3 class="text-base font-semibold text-[var(--nav-text)]">
              {{ plan.name }}
            </h3>

            <p
              class="mt-2 max-w-xs text-sm leading-6 text-[var(--nav-muted)]"
            >
              {{ plan.description }}
            </p>

            <div class="mt-7 flex items-end gap-1">
              <span
                class="text-4xl font-semibold tracking-[-0.05em] text-[var(--nav-text)]"
              >
                {{ plan.price }}
              </span>

              <span
                v-if="plan.price !== 'Custom'"
                class="mb-1 text-xs text-[var(--nav-muted)]"
              >
                / user / month
              </span>
            </div>

            <a
              href="#contact"
              class="mt-7 flex h-11 items-center justify-center rounded-full text-xs font-semibold transition-all duration-300"
              :class="
                plan.popular
                  ? 'bg-[var(--nav-text)] text-[var(--nav-bg)] hover:opacity-80'
                  : 'border border-[var(--nav-border)] text-[var(--nav-text)] hover:bg-[var(--nav-hover)]'
              "
            >
              {{ plan.cta }}
            </a>

            <div class="my-7 h-px bg-[var(--nav-border)]" />

            <p
              class="text-[10px] font-semibold uppercase tracking-[0.16em] text-[var(--nav-muted)]"
            >
              Includes
            </p>

            <ul class="mt-4 space-y-3">
              <li
                v-for="feature in plan.features"
                :key="feature"
                class="flex gap-2 text-xs leading-5 text-[var(--nav-muted)]"
              >
                <Check
                  class="mt-0.5 h-3.5 w-3.5 shrink-0 text-[var(--nav-text)]"
                  aria-hidden="true"
                />
                {{ feature }}
              </li>
            </ul>
          </article>
        </div>
      </div>
    </section>

    <section
      class="border-b border-[var(--nav-border)] py-20 sm:py-24 lg:py-28"
    >
      <div class="mx-auto max-w-4xl px-5 sm:px-6 lg:px-8">
        <div class="reveal text-center">
          <p
            class="text-xs font-semibold uppercase tracking-[0.2em] text-[var(--nav-muted)]"
          >
            FAQ
          </p>

          <h2
            class="mt-4 text-3xl font-semibold tracking-[-0.04em] text-[var(--nav-text)] sm:text-4xl"
          >
            Questions, answered.
          </h2>
        </div>

        <div class="mt-12 border-t border-[var(--nav-border)]">
          <div
            v-for="(faq, index) in faqs"
            :key="faq.question"
            class="reveal border-b border-[var(--nav-border)]"
          >
            <button
              type="button"
              class="flex w-full items-center justify-between gap-6 py-5 text-left focus:outline-none"
              :aria-expanded="openFaq === index"
              @click="toggleFaq(index)"
            >
              <span
                class="text-sm font-semibold text-[var(--nav-text)] sm:text-base"
              >
                {{ faq.question }}
              </span>

              <Plus
                class="h-4 w-4 shrink-0 text-[var(--nav-muted)] transition-transform duration-300"
                :class="{ 'rotate-45': openFaq === index }"
                aria-hidden="true"
              />
            </button>

            <Transition
              enter-active-class="overflow-hidden transition-all duration-300 ease-out"
              enter-from-class="max-h-0 opacity-0"
              enter-to-class="max-h-40 opacity-100"
              leave-active-class="overflow-hidden transition-all duration-200 ease-in"
              leave-from-class="max-h-40 opacity-100"
              leave-to-class="max-h-0 opacity-0"
            >
              <div
                v-if="openFaq === index"
                class="max-w-3xl pb-5 pr-8 text-sm leading-6 text-[var(--nav-muted)]"
              >
                {{ faq.answer }}
              </div>
            </Transition>
          </div>
        </div>
      </div>
    </section>

    <section
      class="border-b border-[var(--nav-border)] bg-[var(--nav-text)] py-20 text-[var(--nav-bg)] sm:py-24 lg:py-28"
    >
      <div class="mx-auto max-w-5xl px-5 text-center sm:px-6 lg:px-8">
        <div class="reveal">
          <p class="text-xs font-semibold uppercase tracking-[0.2em] opacity-60">
            Ready when you are
          </p>

          <h2
            class="mx-auto mt-5 max-w-3xl text-4xl font-semibold tracking-[-0.05em] sm:text-5xl lg:text-6xl"
          >
            Give your team a better way to work.
          </h2>

          <p
            class="mx-auto mt-5 max-w-xl text-sm leading-6 opacity-65 sm:text-base"
          >
            Bring your projects, people, and progress together with Flow.
          </p>

          <a
            href="#contact"
            class="mt-8 inline-flex h-12 items-center justify-center rounded-full bg-[var(--nav-bg)] px-7 text-sm font-semibold text-[var(--nav-text)] transition-all duration-300 hover:-translate-y-0.5 hover:shadow-2xl focus:outline-none focus-visible:ring-2 focus-visible:ring-[var(--nav-bg)] focus-visible:ring-offset-2 focus-visible:ring-offset-[var(--nav-text)]"
          >
            Get started
          </a>
        </div>
      </div>
    </section>

    <section
      id="contact"
      class="border-b border-[var(--nav-border)] py-20 sm:py-24 lg:py-28"
    >
      <div class="mx-auto max-w-7xl px-5 sm:px-6 lg:px-8">
        <div class="grid gap-12 lg:grid-cols-[0.8fr_1.2fr] lg:gap-20">
          <div class="reveal">
            <p
              class="text-xs font-semibold uppercase tracking-[0.2em] text-[var(--nav-muted)]"
            >
              Contact
            </p>

            <h2
              class="mt-4 text-3xl font-semibold tracking-[-0.04em] text-[var(--nav-text)] sm:text-4xl"
            >
              Let's talk about your workflow.
            </h2>

            <p
              class="mt-5 max-w-md text-sm leading-7 text-[var(--nav-muted)]"
            >
              Have questions about Flow or want to see how it could fit your
              team? Send us a message and we'll get back to you.
            </p>
          </div>

          <form
            class="reveal space-y-5"
            @submit.prevent="handleContactSubmit"
          >
            <div class="grid gap-5 sm:grid-cols-2">
              <label class="block">
                <span
                  class="mb-2 block text-xs font-medium text-[var(--nav-text)]"
                >
                  Name
                </span>

                <input
                  v-model="contactForm.name"
                  type="text"
                  name="name"
                  required
                  placeholder="Your name"
                  class="h-12 w-full rounded-xl border border-[var(--nav-border)] bg-[var(--nav-surface)] px-4 text-sm text-[var(--nav-text)] outline-none transition-all duration-300 placeholder:text-[var(--nav-muted)] focus:border-[var(--nav-text)] focus:ring-2 focus:ring-[var(--nav-text)]/10"
                />
              </label>

              <label class="block">
                <span
                  class="mb-2 block text-xs font-medium text-[var(--nav-text)]"
                >
                  Email
                </span>

                <input
                  v-model="contactForm.email"
                  type="email"
                  name="email"
                  required
                  placeholder="you@company.com"
                  class="h-12 w-full rounded-xl border border-[var(--nav-border)] bg-[var(--nav-surface)] px-4 text-sm text-[var(--nav-text)] outline-none transition-all duration-300 placeholder:text-[var(--nav-muted)] focus:border-[var(--nav-text)] focus:ring-2 focus:ring-[var(--nav-text)]/10"
                />
              </label>
            </div>

            <label class="block">
              <span
                class="mb-2 block text-xs font-medium text-[var(--nav-text)]"
              >
                Message
              </span>

              <textarea
                v-model="contactForm.message"
                name="message"
                required
                rows="6"
                placeholder="Tell us what you're working on..."
                class="w-full resize-none rounded-xl border border-[var(--nav-border)] bg-[var(--nav-surface)] p-4 text-sm leading-6 text-[var(--nav-text)] outline-none transition-all duration-300 placeholder:text-[var(--nav-muted)] focus:border-[var(--nav-text)] focus:ring-2 focus:ring-[var(--nav-text)]/10"
              />
            </label>

            <div
              class="flex flex-col gap-4 sm:flex-row sm:items-center sm:justify-between"
            >
              <p
                v-if="contactSubmitted"
                class="text-xs text-[var(--nav-muted)]"
              >
                Thanks. Your message is ready to be connected to a backend.
              </p>

              <span v-else />

              <button
                type="submit"
                class="inline-flex h-12 items-center justify-center rounded-full bg-[var(--nav-text)] px-7 text-sm font-semibold text-[var(--nav-bg)] transition-all duration-300 hover:-translate-y-0.5 hover:shadow-xl focus:outline-none focus-visible:ring-2 focus-visible:ring-[var(--nav-text)] focus-visible:ring-offset-2"
              >
                Send message
              </button>
            </div>
          </form>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
import {
  Activity,
  ArrowRight,
  BarChart3,
  Check,
  CheckCircle2,
  Clock3,
  FolderKanban,
  Github,
  LineChart,
  Plus,
  Send,
  Users,
} from 'lucide-vue-next';

export default {
  name: 'PageContent',

  components: {
    Activity,
    ArrowRight,
    BarChart3,
    Check,
    CheckCircle2,
    Clock3,
    FolderKanban,
    Github,
    LineChart,
    Plus,
    Send,
    Users,
  },

  data() {
    return {
      dashboardSidebar: [
        'Overview',
        'My tasks',
        'Inbox',
        'Calendar',
      ],

      dashboardProjects: [
        'Product Launch',
        'Website Redesign',
        'Mobile App',
      ],

      dashboardAvatars: ['JD', 'AM', 'RK', 'SL'],

      dashboardStats: [
        {
          label: 'Tasks completed',
          value: '128',
          detail: '+18%',
        },
        {
          label: 'Project progress',
          value: '74%',
          detail: 'On track',
        },
        {
          label: 'Days remaining',
          value: '12',
          detail: 'Healthy',
        },
      ],

      kanbanColumns: [
        {
          title: 'To do',
          items: [
            {
              title: 'Finalize onboarding flow',
              tag: 'Product',
              date: 'Today',
              progress: 0,
            },
            {
              title: 'Prepare launch checklist',
              tag: 'Launch',
              date: 'Tomorrow',
              progress: 0,
            },
          ],
        },
        {
          title: 'In progress',
          items: [
            {
              title: 'Build analytics dashboard',
              tag: 'Engineering',
              date: 'Today',
              progress: 68,
            },
            {
              title: 'Review marketing assets',
              tag: 'Marketing',
              date: 'Fri',
              progress: 42,
            },
          ],
        },
        {
          title: 'Done',
          items: [
            {
              title: 'Create project roadmap',
              tag: 'Planning',
              date: 'Done',
              progress: 100,
            },
            {
              title: 'Set up team workspace',
              tag: 'Operations',
              date: 'Done',
              progress: 100,
            },
          ],
        },
      ],

      companyLogos: [
        'Northstar',
        'Vertex',
        'Arc',
        'Monument',
        'Parallel',
        'Horizon',
      ],

      features: [
        {
          title: 'Project organization',
          description:
            'Keep every project, milestone, document, and decision organized in one focused workspace.',
          icon: FolderKanban,
        },
        {
          title: 'Task management',
          description:
            'Turn plans into actionable tasks with priorities, owners, statuses, and clear deadlines.',
          icon: CheckCircle2,
        },
        {
          title: 'Team collaboration',
          description:
            'Keep conversations connected to the work with comments, mentions, and shared context.',
          icon: Users,
        },
        {
          title: 'Progress tracking',
          description:
            'Understand project health at a glance with clear progress indicators and project views.',
          icon: Activity,
        },
        {
          title: 'Deadline control',
          description:
            'Stay ahead of important dates with timelines, reminders, and workload visibility.',
          icon: Clock3,
        },
        {
          title: 'Project analytics',
          description:
            'Use meaningful insights to understand team velocity and make better decisions.',
          icon: BarChart3,
        },
      ],

      steps: [
        {
          number: '01',
          title: 'Create a project',
          description:
            'Set up your workspace, define milestones, and turn your goals into a clear plan.',
        },
        {
          number: '02',
          title: 'Invite your team',
          description:
            'Bring everyone into one workspace with clear ownership and shared visibility.',
        },
        {
          number: '03',
          title: 'Track and ship',
          description:
            'Monitor progress, resolve blockers, and move work from idea to completion.',
        },
      ],

      activities: [
        {
          initials: 'AM',
          name: 'Alex Morgan',
          action: 'commented on',
          comment:
            'The new direction looks good. I think we can ship this version tomorrow.',
          time: '2 minutes ago',
        },
        {
          initials: 'RK',
          name: 'Ryan Kim',
          action: 'completed a task',
          comment: '',
          time: '18 minutes ago',
        },
        {
          initials: 'SL',
          name: 'Sarah Lee',
          action: 'moved a task to In Progress',
          comment: '',
          time: '42 minutes ago',
        },
      ],

      analyticsStats: [
        {
          target: 98,
          suffix: '%',
          label: 'on-time delivery',
        },
        {
          target: 3,
          suffix: 'x',
          label: 'faster project execution',
        },
        {
          target: 10,
          suffix: 'k+',
          label: 'teams using Flow',
        },
      ],

      chartBars: [30, 42, 38, 57, 51, 68, 73, 88],

      testimonials: [
        {
          initials: 'JC',
          name: 'Jordan Chen',
          role: 'Product Lead',
          company: 'Northstar',
          quote:
            'Flow replaced three separate tools for our team. Everyone knows what matters and what needs to happen next.',
        },
        {
          initials: 'AM',
          name: 'Avery Morgan',
          role: 'Head of Design',
          company: 'Arc',
          quote:
            'The simplicity is what sold us. There is enough power for complex projects without the usual clutter.',
        },
        {
          initials: 'RK',
          name: 'Ryan Kim',
          role: 'Engineering Manager',
          company: 'Vertex',
          quote:
            'Our weekly planning is dramatically faster. Flow gives engineering and product one shared source of truth.',
        },
      ],

      billingCycle: 'monthly',

      pricingPlans: [
        {
          name: 'Starter',
          description: 'For small teams building their workflow.',
          monthlyPrice: '$8',
          yearlyPrice: '$6',
          price: '$8',
          cta: 'Start for free',
          popular: false,
          features: [
            'Up to 10 team members',
            'Unlimited projects',
            'Task and project views',
            'Basic analytics',
            '7-day activity history',
          ],
        },
        {
          name: 'Pro',
          description: 'For growing teams that need more control.',
          monthlyPrice: '$16',
          yearlyPrice: '$13',
          price: '$16',
          cta: 'Start free trial',
          popular: true,
          features: [
            'Unlimited team members',
            'Advanced project views',
            'Custom workflows',
            'Advanced analytics',
            'Unlimited activity history',
          ],
        },
        {
          name: 'Enterprise',
          description: 'For organizations with complex workflows.',
          monthlyPrice: 'Custom',
          yearlyPrice: 'Custom',
          price: 'Custom',
          cta: 'Talk to sales',
          popular: false,
          features: [
            'Everything in Pro',
            'Advanced permissions',
            'Priority support',
            'Security controls',
            'Custom onboarding',
          ],
        },
      ],

      faqs: [
        {
          question: 'Can I try Flow before paying?',
          answer:
            'Yes. Flow offers a free trial so your team can experience the core workflow before choosing a paid plan.',
        },
        {
          question: 'Can Flow work for larger teams?',
          answer:
            'Absolutely. The Enterprise plan is designed for larger organizations that need advanced permissions, security controls, and dedicated support.',
        },
        {
          question: 'Can I invite people from different teams?',
          answer:
            'Yes. You can organize projects and invite collaborators across departments while keeping project ownership and permissions clear.',
        },
        {
          question: 'Does Flow replace our existing tools?',
          answer:
            'Flow is designed to bring project planning, task management, collaboration, and progress tracking into one focused workspace.',
        },
        {
          question: 'Can I change plans later?',
          answer:
            'Yes. You can upgrade or change your plan as your team and workflow requirements evolve.',
        },
      ],

      openFaq: null,

      contactForm: {
        name: '',
        email: '',
        message: '',
      },

      contactSubmitted: false,

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

  watch: {
    billingCycle(value) {
      this.pricingPlans.forEach((plan) => {
        plan.price =
          value === 'yearly'
            ? plan.yearlyPrice
            : plan.monthlyPrice;
      });
    },
  },

  mounted() {
    this.setupRevealAnimations();
    this.setupCounters();
  },

  methods: {
    toggleFaq(index) {
      this.openFaq = this.openFaq === index ? null : index;
    },

    handleContactSubmit() {
      this.contactSubmitted = true;
    },

    setupRevealAnimations() {
      const elements = document.querySelectorAll('.reveal');

      const observer = new IntersectionObserver(
        (entries, currentObserver) => {
          entries.forEach((entry) => {
            if (entry.isIntersecting) {
              entry.target.classList.add('is-visible');
              currentObserver.unobserve(entry.target);
            }
          });
        },
        {
          threshold: 0.12,
        },
      );

      elements.forEach((element) => observer.observe(element));
    },

    setupCounters() {
      const counters = document.querySelectorAll('.counter');

      const observer = new IntersectionObserver(
        (entries, currentObserver) => {
          entries.forEach((entry) => {
            if (!entry.isIntersecting) {
              return;
            }

            const element = entry.target;
            const target = Number(element.dataset.target);
            const suffix = element.dataset.suffix || '';
            const duration = 1200;
            const startTime = performance.now();

            const updateCounter = (currentTime) => {
              const progress = Math.min(
                (currentTime - startTime) / duration,
                1,
              );

              const easedProgress =
                1 - Math.pow(1 - progress, 3);

              const currentValue = Math.floor(
                target * easedProgress,
              );

              element.textContent = `${currentValue}${suffix}`;

              if (progress < 1) {
                requestAnimationFrame(updateCounter);
              } else {
                element.textContent = `${target}${suffix}`;
              }
            };

            requestAnimationFrame(updateCounter);
            currentObserver.unobserve(element);
          });
        },
        {
          threshold: 0.5,
        },
      );

      counters.forEach((counter) => observer.observe(counter));
    },
  },
};
</script>

<style scoped>
.reveal {
  opacity: 0;
  transform: translateY(24px);
  transition:
    opacity 700ms cubic-bezier(0.22, 1, 0.36, 1),
    transform 700ms cubic-bezier(0.22, 1, 0.36, 1);
}

.reveal.is-visible {
  opacity: 1;
  transform: translateY(0);
}

.dashboard-preview {
  transform: perspective(1600px) rotateX(1deg);
  transform-origin: center top;
}

@media (max-width: 767px) {
  .dashboard-preview {
    transform: none;
  }
}

@media (prefers-reduced-motion: reduce) {
  .reveal {
    opacity: 1;
    transform: none;
    transition: none;
  }

  .dashboard-preview {
    transform: none;
  }
}
</style>