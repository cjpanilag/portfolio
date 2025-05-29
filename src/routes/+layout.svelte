<script>
  import "../app.css";
  const socials = [
    {
      name: "GitHub",
      url: "https://github.com/cjpanilag",
      icon: '<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.3 3.438 9.8 8.207 11.387.6.113.793-.26.793-.577v-2.234c-3.338.726-4.042-1.61-4.042-1.61-.546-1.387-1.333-1.756-1.333-1.756-1.09-.746.083-.73.083-.73 1.205.084 1.838 1.237 1.838 1.237 1.07 1.835 2.807 1.305 3.492.997.108-.774.42-1.305.763-1.605-2.665-.3-5.467-1.333-5.467-5.93 0-1.31.468-2.382 1.237-3.222-.123-.303-.536-1.523.117-3.176 0 0 1.01-.323 3.3 1.23.96-.267 1.987-.4 3.007-.405 1.02.005 2.047.138 3.007.405 2.29-1.553 3.3-1.23 3.3-1.23.653 1.653.24 2.873.117 3.176.77.84 1.237 1.912 1.237 3.222 0 4.61-2.807 5.625-5.48 5.92.432.372.816 1.102.816 2.222v3.293c0 .32.192.694.8.577C20.565 21.8 24 17.3 24 12c0-6.63-5.37-12-12-12z"/></svg>',
    },
    {
      name: "LinkedIn",
      url: "https://linkedin.com/in/yourusername",
      icon: '<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6"><path d="M19 0H5C2.24 0 0 2.24 0 5v14c0 2.76 2.24 5 5 5h14c2.76 0 5-2.24 5-5V5c0-2.76-2.24-5-5-5zM8.34 19H5.67V9h2.67v10zm-1.34-11.5c-.86 0-1.5-.64-1.5-1.5s.64-1.5 1.5-1.5 1.5.64 1.5 1.5-.64 1.5-1.5 1.5zM19 19h-2.67v-5.5c0-1.32-.48-2.22-1.68-2.22-.92 0-1.47.62-1.71 1.22-.09.22-.11.52-.11.82V19h-2.67s.04-8.5 0-10h2.67v1.42c.36-.56 1-1.36 2.44-1.36 1.78 0 3.11 1.16 3.11 3.66V19z"/></svg>',
    },
    {
      name: "Twitter",
      url: "https://twitter.com/yourusername",
      icon: '<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6"><path d="M24 4.56c-.89.39-1.84.65-2.84.77a4.92 4.92 0 0 0 2.15-2.71 9.86 9.86 0 0 1-3.13 1.2 4.92 4.92 0 0 0-8.38 4.48A13.94 13.94 0 0 1 1.67 3.15a4.92 4.92 0 0 0 1.52 6.56 4.9 4.9 0 0 1-2.23-.62v.06a4.92 4.92 0 0 0 3.95 4.83 4.93 4.93 0 0 1-2.22.08 4.92 4.92 0 0 0 4.6 3.42A9.86 9.86 0 0 1 0 19.54a13.9 13.9 0 0 0 7.55 2.21c9.05 0 14-7.5 14-14 0-.21 0-.42-.02-.63A10.02 10.02 0 0 0 24 4.56z"/></svg>',
    },
  ];
</script>

<!-- Header -->
<header
  class="sticky top-0 flex justify-between items-center px-6 py-4 text-sm text-cyan-900 font-mono z-50"
>
  <a class="animate-slide-in-left" href="/">cjpanilag@gmail.com</a>
  <nav class="space-x-6 animate-slide-in-right">
    <a href="/about" class="hover:underline">About</a>
    <a href="#works" class="hover:underline">Works</a>
  </nav>
</header>

<!-- Side Panel -->
<section
  class="fixed right-4 top-1/2 transform -translate-y-1/2 flex flex-col space-y-4 text-xl text-gray-500 z-10 animate-slide-in-right"
>
  {#each socials as social}
    <a
      href={social.url}
      target="_blank"
      rel="noopener noreferrer"
      class="hover:text-blue-500"
      title={social.name}
    >
      {@html social.icon}
    </a>
  {/each}
</section>

<main class="flex flex-col items-center justify-center min-h-screen px-6">
  <slot />
</main>

<style lang="postcss">
  @reference "tailwindcss";
  :global(html) {
    background-color: theme(--color-amber-100);
  }
</style>
