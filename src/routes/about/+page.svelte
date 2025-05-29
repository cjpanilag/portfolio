<script lang="ts">
  import VerticalTimeline from "$lib/components/VerticalTimeline.svelte";

  const yearOfExp = 6;

  let myTimelineEvents = [
    {
      id: 1,
      date: "2023 - Present",
      title: "Chief Innovator",
      company: "Future Solutions",
      description:
        "Pioneering new technologies and dreaming big, leading multiple high-impact projects to success.",
      icon: "rocket",
    },
    {
      id: 2,
      date: "2020 - 2023", // Overall tenure at this company
      title: "Senior Engineering Lead", // Final or most significant title at this company
      company: "Tech Builders Co.",
      description:
        "Grew within the company, contributing to core product development and eventually leading a team of 5 engineers.", // Overall summary
      icon: "code",
      subEventsTitle: "Career Growth at Tech Builders", // Optional: Custom title for the sub-section
      subEvents: [
        // Promotions or key milestones listed (e.g., newest first)
        {
          id: "2a",
          date: "May 2022 - April 2023",
          title: "Senior Engineering Lead",
          description:
            "Led the 'Phoenix Project' team, responsible for architecture and delivery.",
        },
        {
          id: "2b",
          date: "Jan 2021 - May 2022",
          title: "Promoted to Software Engineer II",
          description:
            "Took on more complex tasks and began mentoring junior developers.",
        },
        {
          id: "2c",
          date: "March 2020 - Jan 2021",
          title: "Joined as Software Engineer I",
          description:
            "Contributed to backend services and feature development.",
        },
      ],
    },
    {
      id: 3,
      date: "2018 - 2020",
      title: "Junior Coder",
      company: "Startup X",
      description:
        "Learned the ropes and fixed many bugs. Gained foundational experience in full-stack development.",
      icon: "briefcase",
    },
    {
      id: 4,
      date: "Education",
      title: "B.Sc. Computer Science",
      company: "University of Svelte",
      description:
        "Graduated with honors, specializing in software development principles.",
      icon: "gradcap",
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
