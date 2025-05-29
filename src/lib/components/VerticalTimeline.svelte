<script context="module" lang="ts">
  export type SubEvent = {
    id: string;
    date: string;
    title: string;
    description?: string;
  };

  export type TimelineItem = {
    id: number | string;
    date: string;
    title: string;
    company?: string;
    description: string;
    icon?: string;
    subEventsTitle?: string;
    subEvents?: SubEvent[];
    [key: string]: any;
  };
</script>

<script lang="ts">
  export let items: TimelineItem[] = [];

  const iconMap: { [key: string]: string } = {
    default: "📅",
    briefcase: "💼",
    code: "💻",
    rocket: "🚀",
    star: "⭐",
    gradcap: "🎓",
    tools: "🛠️",
    award: "🏆",
    milestone: "🚩",
    event: "🎉",
    update: "📢",
  };

  function getIconEmoji(iconName?: string): string {
    if (!iconName) return iconMap.default;
    return iconMap[iconName] || iconName || iconMap.default;
  }
</script>

<div class="container mx-auto px-4 sm:px-6 lg:px-8 py-12 font-sans">
  <div class="relative wrap overflow-hidden p-2 md:p-10 h-full">
    <div
      class="absolute h-full border-opacity-50 border-cyan-700 bg-cyan-700/60 hidden md:block rounded-full"
      style="left: 50%; top: 0; width: 4px; transform: translateX(-50%); z-index: 0;"
    ></div>
    <div
      class="absolute h-full border-opacity-50 border-cyan-700 bg-cyan-700/60 md:hidden rounded-full"
      style="left: 20px; top: 0; width: 4px; transform: translateX(-50%); z-index: 0;"
    ></div>

    {#each items as item, index (item.id)}
      <div
        class="mb-10 flex w-full items-start
               md:justify-between {index % 2 === 0
          ? 'md:flex-row-reverse'
          : 'md:flex-row'}"
      >
        <div class="w-0 md:w-[calc(50%-2.75rem)] hidden md:block"></div>

        <div
          class="z-10 order-1 shrink-0
                 flex items-center justify-center
                 bg-cyan-600 shadow-xl w-11 h-11 rounded-full
                 ring-4 ring-white dark:ring-slate-900
                 ring-offset-2 ring-offset-white dark:ring-offset-slate-900
                 mr-3 md:mr-0
                "
          style="margin-left: calc(20px - (2.75rem / 2));"
          class:md:ml-0={true}
        >
          <span class="text-xl md:text-2xl text-white"
            >{getIconEmoji(item.icon)}</span
          >
        </div>

        <div
          class="order-1 bg-white dark:bg-slate-800 rounded-xl shadow-2xl
                 w-full md:w-[calc(50%-2.75rem)] p-5 md:p-6
                 relative
                 border-l-4 md:border-l-0 {index % 2 === 0
            ? 'md:border-r-4 md:border-l-0'
            : 'md:border-l-4 md:border-r-0'} border-cyan-500
                 transform transition-all duration-300 ease-in-out hover:scale-[1.02] hover:shadow-cyan-500/40 dark:hover:shadow-cyan-400/30"
        >
          <div
            class="absolute top-5 -left-[9px] w-[18px] h-[18px] bg-white dark:bg-slate-800 transform rotate-45 md:hidden z-0"
          ></div>
          <div
            class="hidden md:block absolute top-6 w-5 h-5 bg-white dark:bg-slate-800 transform rotate-45 z-0
                      {index % 2 === 0 ? '-right-2.5' : '-left-2.5'}"
          ></div>

          <div class="relative z-10">
            <div
              class="flex flex-col sm:flex-row sm:items-center sm:justify-between mb-2"
            >
              <h3
                class="font-bold text-cyan-900 dark:text-cyan-100 text-lg sm:text-xl md:text-2xl mb-1 sm:mb-0"
              >
                {item.title}
              </h3>
              {#if item.company}
                <span
                  class="text-xs font-mono text-cyan-700 dark:text-cyan-300 bg-cyan-50 dark:bg-slate-700/50 px-3 py-1 rounded-full whitespace-nowrap self-start sm:self-center mt-1 sm:mt-0"
                >
                  {item.company}
                </span>
              {/if}
            </div>
            <p
              class="text-sm font-semibold text-cyan-600 dark:text-cyan-400 mb-3"
            >
              {item.date}
            </p>
            <p
              class="text-gray-700 dark:text-slate-300 text-base leading-relaxed"
            >
              {item.description}
            </p>

            {#if item.subEvents && item.subEvents.length > 0}
              <div
                class="mt-5 pt-4 border-t border-gray-200 dark:border-slate-700"
              >
                <h4
                  class="text-sm font-semibold text-cyan-800 dark:text-cyan-200 mb-3"
                >
                  {item.subEventsTitle || "Key Milestones"}
                </h4>
                <div class="space-y-4">
                  {#each item.subEvents as subEvent (subEvent.id)}
                    <div class="flex items-start">
                      <div class="shrink-0 mt-1 mr-3">
                        <div
                          class="w-2.5 h-2.5 bg-cyan-500 dark:bg-cyan-400 rounded-full ring-1 ring-offset-1 ring-cyan-300 dark:ring-cyan-600 ring-offset-white dark:ring-offset-slate-800"
                        ></div>
                      </div>
                      <div class="flex-grow">
                        <p
                          class="text-xs font-semibold text-gray-700 dark:text-slate-200 leading-tight"
                        >
                          {subEvent.title}
                        </p>
                        <p
                          class="text-xs text-gray-500 dark:text-slate-400 mb-0.5 leading-tight"
                        >
                          {subEvent.date}
                        </p>
                        {#if subEvent.description}
                          <p
                            class="text-xs text-gray-600 dark:text-slate-300 leading-snug"
                          >
                            {subEvent.description}
                          </p>
                        {/if}
                      </div>
                    </div>
                  {/each}
                </div>
              </div>
            {/if}
          </div>
        </div>
      </div>
    {/each}
  </div>
</div>

<style>
  /*
    To ensure md:ml-0 overrides the inline style for margin-left on the dot container:
    You can add `!important` to the Tailwind class if necessary, like `md:!ml-0`.
    However, Svelte's class directive `class:md:ml-0={true}` applies the class, and standard CSS specificity rules apply.
    The inline `style` attribute has very high specificity.
    A more robust way to handle conditional styling that needs to override inline styles for specific breakpoints
    is often to manage the inline style value itself conditionally within the <script> block or use CSS variables.

    For simplicity here, the inline style is applied for mobile, and we rely on `md:mr-0` (and implicit `md:ml-0` by not being `mr-auto` or `ml-auto`)
    for desktop flex item centering. The `class:md:ml-0={true}` is a good measure.
    If precise override is needed:
  */
  @media (min-width: 768px) {
    /* md breakpoint */
    .z-10.order-1.shrink-0.flex.items-center.justify-center {
      /* Target the dot container specifically */
      margin-left: 0 !important; /* Override the inline style for mobile */
    }
  }
</style>
