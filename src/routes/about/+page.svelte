<script lang="ts">
  import VerticalTimeline from "$lib/components/VerticalTimeline.svelte";

  const yearOfExp = 6;

  let myTimelineEvents = [
    {
      id: 1,
      date: "2022 - Present",
      title: "Technical Lead - Software Engineer",
      company: "Fligno",
      description:
        "Pioneering new technologies and dreaming big, leading multiple high-impact projects to success.",
      icon: "briefcase",
      subEvents: [
        {
          id: "1a",
          date: "May 2025 - Present",
          title: "Technical Lead",
          description:
            "Troubleshoot and resolve complex technical issues across the development stack.",
        },
        {
          id: "2a",
          date: "April 2022 - May 2025",
          title: "Software Engineer",
          description:
            "Collaborated with cross-functional teams to design and implement scalable software solutions.",
        },
      ],
    },
    {
      id: 2,
      date: "Oct 2024 - May 2025",
      title: "Software Engineer", // Final or most significant title at this company
      company: "ChangeGPS",
      description: "An Accounting Service Platform created under fligno.", // Overall summary
      icon: "code",
    },
    {
      id: 3,
      date: "Sept 2022 - Feb 2023",
      title: "Software Engineer",
      company: "Paiid",
      description: "Tap to Pay App created also under fligno.",
      icon: "briefcase",
    },
    {
      id: 4,
      date: "Apr 2022 - Sep 2022",
      title: "Software Engineer",
      company: "FIN-PAY",
      description:
        "A Fintech company that provides a payment platform for businesses.",
      icon: "code",
    },
    {
      id: 5,
      date: "Apr 2021 - Apr 2022",
      title: "Software Engineer",
      company: "Fourello",
      description: "A platform that connects freelancers with clients.",
      icon: "rocket",
      subEvents: [
        {
          id: "5a",
          date: "Apr 2021 - Apr 2022",
          title: "Event and Data Engineer",
          description:
            "Responsible for data processing and event management tools development.",
        },
        {
          id: "5b",
          date: "Apr 2021 - Apr 2022",
          title: "J.R Sotware Engineer",
          description:
            "Assisted in the development of web applications and services.",
        },
      ],
    },
  ];
</script>

<section
  class="flex flex-col mt-12 md:flex-row items-center gap-6 max-w-5xl w-full"
>
  <div class="md:w-full md:text-center space-y-6 animate-slide-in-left">
    <h1 class="text-8xl text-cyan-900 font-bold">
      {yearOfExp}+ Years as a Software Engineer
    </h1>
    <!-- <p class="text-2xl text-center font-mono text-gray-500">Software Engineer</p> -->
  </div>
</section>
<section class="flex flex-col md:flex-row items-center gap-6 max-w-5xl w-full">
  <VerticalTimeline items={myTimelineEvents} />
</section>
