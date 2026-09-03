---
theme: default
title: Unified Student Portal — AI Course Recommendation Engine
titleTemplate: '%s'
favicon: '/fav-icon.svg'
info: |
  ## Unified Student Portal with an AI-based Course Recommendation Engine
  Design and development of a layered student portal architecture with a hybrid recommender.
  Undergraduate Capstone Project Presentation — Alireza Hassani Eghtedar
class: text-[#EAF0FA]
colorSchema: dark
background: 'radial-gradient(ellipse at 50% -10%, #131A3A 0%, #0A0E24 55%, #05070F 100%)'
transition: fade
mdc: true
fonts:
  sans: 'Inter'
  serif: 'Space Grotesk:500,600,700'
  mono: 'JetBrains Mono'
---

<!-- ============ SIGNATURE: reusable "portal node-line" side rail ============
The whole project is about connecting many separate campus systems through
one hub. Instead of the HUD deck's speed-tape rail, this deck reuses a
vertical line of connected nodes down the left margin — a small dot for
every "system" being unified, joined by a single spine. It is the one
recurring signature element on content slides. -->

<div class="relative flex flex-col items-center justify-center h-full text-center px-20">
  <div class="font-mono text-xs tracking-[0.45em] text-[#4DA3FF] mb-6">CAPSTONE PROJECT</div>
  <h1 class="font-serif font-700 uppercase text-5xl leading-[1.05] text-[#F3F6FC]" style="letter-spacing: 0.01em;">
    Unified Student Portal<br>+ AI Course Recommender
  </h1>
  <div class="font-mono text-sm tracking-[0.25em] text-[#93A2C4] mt-6 uppercase">
    One login, six services, one recommendation engine
  </div>
  <div class="flex items-center gap-3 my-4">
    <div class="w-16 h-px bg-[#4DA3FF]/50"></div>
    <div class="w-1.5 h-1.5 rounded-full bg-[#4DA3FF]"></div>
    <div class="w-16 h-px bg-[#4DA3FF]/50"></div>
  </div>
  <div class="font-mono text-xs text-[#7C89AD] leading-relaxed">
    Alireza Hassani Eghtedar &nbsp;·&nbsp; Student ID 992023008<br>
    Supervisor: Dr. Jalalian &nbsp;·&nbsp; Kharazmi University — Computer Engineering
  </div>
</div>

<div @click="$slidev.nav.next" class="absolute bottom-8 right-14 font-mono text-xs text-[#4DA3FF] flex items-center gap-2 cursor-pointer opacity-70 hover:opacity-100">
  PRESS SPACE <carbon:arrow-right />
</div>

<!--
Title slide: introduce yourself, the course, and the instructor. One line on the
core problem: students juggle many disconnected university systems, and course
selection happens with no data-driven guidance.
-->

---
transition: fade
---

<div class="portal-rail"></div>

<div class="h-full flex flex-col justify-center pl-28 pr-20">

<div class="font-mono text-xs tracking-[0.35em] text-[#4DA3FF] mb-3">§ 01 — INTRODUCTION</div>
<h1 class="font-serif font-700 uppercase text-4xl text-[#F3F6FC] mb-10">Problem Statement</h1>

<div class="grid grid-cols-[1fr_auto] gap-10 items-start">
<div class="space-y-5 font-sans text-lg text-[#D6DEF0]">

<v-clicks>

- Students juggle **many independent systems** — courses, welfare fund, dorms, library, advising
- Each system has its **own login, password, and interface**
- An outage or bug in any one of them can block something critical, like **course registration**
- Elective course selection is mostly **word-of-mouth**, with no personalized, data-driven guidance
- The result is a **fragmented student experience**, repeated logins, and wasted time

</v-clicks>

</div>

<div class="w-56 pt-2">
<v-motion :initial="{ opacity: 0 }" :enter="{ opacity: 1, transition: { delay: 800 } }">
<div class="border border-[#212A4A] bg-[#0E1330] p-4 font-mono text-xs text-[#93A2C4] leading-relaxed">
  <div class="text-[#4DA3FF] mb-1">// TYPICAL STACK</div>
  Golestan · Welfare fund<br>Dorms · Library · Advising
</div>
</v-motion>
</div>

</div>

<v-click>
<div class="mt-1 border-l-2 border-[#4DA3FF] pl-5 py-2 bg-[#4DA3FF]/5 max-w-2xl">
  <span class="font-mono text-xs text-[#4DA3FF]">RESEARCH QUESTION</span>
  <div class="text-[#F3F6FC] mt-1">How can these scattered services be brought under one unified portal, and course selection made smarter using the student's own history and interests?</div>
</div>
</v-click>

</div>

---
transition: fade
---

<div class="portal-rail"></div>

<div class="h-full flex flex-col justify-center pl-28 pr-20">

<div class="font-mono text-xs tracking-[0.35em] text-[#4DA3FF] mb-3">§ 01 — INTRODUCTION</div>
<h1 class="font-serif font-700 uppercase text-4xl text-[#F3F6FC] mb-10">Why It Matters</h1>

<div class="flex flex-col gap-3 max-w-3xl">
  <div v-for="(item, i) in [
      { tag: 'PERSONAL', title: 'Individual level', desc: 'Less time and energy lost switching between systems — more room for actual learning and planning.' },
      { tag: 'INSTITUTION', title: 'Institutional level', desc: 'Unified student data enables better decisions — spotting in-demand courses or students at academic risk.' },
      { tag: 'TECHNOLOGY', title: 'Technical level', desc: 'A full software-engineering cycle plus applied machine learning (recommenders) in one real, defensible project.' },
    ]"
    :key="i"
    class="flex gap-5 items-start border-l-2 pl-5 py-3 transition-all duration-300"
    :class="$clicks > i ? 'border-[#4DA3FF] bg-[#4DA3FF]/5' : 'border-[#212A4A] opacity-40'">
    <div class="font-mono text-sm w-28 shrink-0" :class="$clicks > i ? 'text-[#4DA3FF]' : 'text-[#7C89AD]'">{{ item.tag }}</div>
    <div>
      <div class="font-serif font-600 text-lg text-[#F3F6FC]">{{ item.title }}</div>
      <div class="text-sm text-[#93A2C4] mt-1">{{ item.desc }}</div>
    </div>
  </div>
</div>

<v-click at="3">
<div class="mt-8 font-mono text-xs text-[#4DA3FF] max-w-2xl">
  ↗ This makes the topic well-suited for a computer engineering capstone: architecture + a real ML component
</div>
</v-click>

</div>

---
transition: slide-up
---

<div class="portal-rail"></div>

<div class="h-full flex flex-col justify-center pl-28 pr-20">

<div class="font-mono text-xs tracking-[0.35em] text-[#4DA3FF] mb-3">§ 01 — INTRODUCTION</div>
<h1 class="font-serif font-700 uppercase text-4xl text-[#F3F6FC] mb-10">Research Objectives</h1>

<div class="grid grid-cols-2 gap-5 max-w-4xl">

<v-click><div class="border border-[#212A4A] bg-[#0E1330] p-5"><span class="font-mono text-[#4DA3FF] text-sm">01</span><div class="mt-2 text-[#D6DEF0]">Identify and categorize students' pain points with multiple campus systems</div></div></v-click>

<v-click><div class="border border-[#212A4A] bg-[#0E1330] p-5"><span class="font-mono text-[#4DA3FF] text-sm">02</span><div class="mt-2 text-[#D6DEF0]">Review unified student portals, in Iran and internationally</div></div></v-click>

<v-click><div class="border border-[#212A4A] bg-[#0E1330] p-5"><span class="font-mono text-[#4DA3FF] text-sm">03</span><div class="mt-2 text-[#D6DEF0]">Review course-recommender algorithms and pick a fit for course registration</div></div></v-click>

<v-click><div class="border border-[#212A4A] bg-[#0E1330] p-5"><span class="font-mono text-[#4DA3FF] text-sm">04</span><div class="mt-2 text-[#D6DEF0]">Design a layered architecture, a first recommender algorithm, and a UI prototype</div></div></v-click>

</div>

</div>

---
transition: fade
---

<div class="portal-rail"></div>

<div class="h-full flex flex-col justify-center pl-28 pr-20">

<div class="font-mono text-xs tracking-[0.35em] text-[#4DA3FF] mb-3">§ 01 — INTRODUCTION</div>
<h1 class="font-serif font-700 uppercase text-4xl text-[#F3F6FC] mb-10">Research Questions</h1>

<div class="space-y-4 max-w-3xl text-lg text-[#D6DEF0]">
<v-clicks>

- Which pain points with multiple university systems hurt the student experience most?
- What architectural and technology choices have existing unified portals made — strengths and weaknesses?
- Which recommendation approach — collaborative, content-based, or hybrid — best fits a **cold-start**, data-scarce university setting?
- How can one architecture deliver both service integration **and** personalized recommendations, while staying scalable and secure?

</v-clicks>
</div>

</div>

---
transition: fade
---

<div class="portal-rail"></div>

<div class="h-full flex flex-col justify-center pl-28 pr-20">

<div class="font-mono text-xs tracking-[0.35em] text-[#4DA3FF] mb-3">§ 02 — RELATED WORK</div>
<h1 class="font-serif font-700 uppercase text-4xl text-[#F3F6FC] mb-10">The Iranian Landscape</h1>

<div class="space-y-4 max-w-2xl text-lg text-[#D6DEF0]">
<v-clicks>

- Most public universities run academic affairs through the **Golestan** system — registration, drop/add, transcripts, teacher evaluation
- Welfare fund, dorms, library access, and tech support usually live in **entirely separate systems**, each with its own login
- University of Kurdistan's own student-services page lists Golestan, research management, student portal, welfare fund, and dorms **side by side, unconnected**
- Official guides route different problems to **different administrative offices** — a sign there's no single support layer
- Core gap: **no single, unified entry point** for all student services at most Iranian universities

</v-clicks>
</div>

</div>

---
transition: fade
---

<div class="portal-rail"></div>

<div class="h-full flex flex-col justify-center pl-28 pr-20">

<div class="font-mono text-xs tracking-[0.35em] text-[#4DA3FF] mb-3">§ 02 — RELATED WORK</div>
<h1 class="font-serif font-700 uppercase text-4xl text-[#F3F6FC] mb-10">International Landscape</h1>

<div class="space-y-5 max-w-3xl">

<v-click>
<div class="border-b border-[#212A4A] pb-4">
  <div class="font-serif font-600 text-lg text-[#F3F6FC]">"Student Portal" &amp; Single Sign-On <span class="font-mono text-xs text-[#4DA3FF] ml-2">widely adopted</span></div>
  <div class="text-sm text-[#93A2C4] mt-1">Modern portals typically integrate with SIS and LMS platforms and must satisfy scalability and privacy rules such as GDPR / FERPA</div>
</div>
</v-click>

<v-click>
<div class="border-b border-[#212A4A] pb-4">
  <div class="font-serif font-600 text-lg text-[#F3F6FC]">Reddii et al. <span class="font-mono text-xs text-[#4DA3FF] ml-2">IJRASET, 2026</span></div>
  <div class="text-sm text-[#93A2C4] mt-1">A unified digital student portal automating leave requests, dorm exit permits, certificates, and complaint tracking</div>
</div>
</v-click>

<v-click>
<div class="pb-2">
  <div class="font-serif font-600 text-lg text-[#F3F6FC]">Their 4-layer stack <span class="font-mono text-xs text-[#4DA3FF] ml-2">React/Next.js · Node.js · GraphQL · Prisma</span></div>
  <div class="text-sm text-[#93A2C4] mt-1">Workflow automation cut admin request processing from days to minutes, with 1–2 second response times</div>
</div>
</v-click>

</div>

<v-click>
<div class="mt-8 font-mono text-xs text-[#4DA3FF] max-w-2xl">
  → This 4-layer pattern inspired our architecture — but their work stops at admin workflows, with no course recommender
</div>
</v-click>

</div>

---

<div class="portal-rail"></div>

<div class="h-full flex flex-col justify-center pl-28 pr-20">

<div class="font-mono text-xs tracking-[0.35em] text-[#4DA3FF] mb-3">§ 02 — RELATED WORK</div>
<h1 class="font-serif font-700 uppercase text-4xl text-[#F3F6FC] mb-2">Course Recommender Approaches</h1>
<div class="text-sm text-[#7C89AD] mb-8">three families from the literature</div>

<div class="flex flex-col gap-3 max-w-3xl">
  <div v-for="(item, i) in [
      { tag: 'CF', title: 'Collaborative Filtering', desc: 'Predicts interest from similarity to other students (user-based) or similarity among courses by shared enrollment (item-based).' },
      { tag: 'CB', title: 'Content-Based Filtering', desc: 'Recommends courses whose syllabus content matches the student’s history and stated interests.' },
      { tag: 'HYBRID', title: 'Hybrid approaches', desc: 'Combine both — better accuracy and resilience against the cold-start problem when behavioral data is scarce.' },
    ]"
    :key="i"
    class="flex gap-5 items-start border-l-2 pl-5 py-3 transition-all duration-300"
    :class="$clicks > i ? 'border-[#4DA3FF] bg-[#4DA3FF]/5' : 'border-[#212A4A] opacity-40'">
    <div class="font-mono text-sm w-16 shrink-0" :class="$clicks > i ? 'text-[#4DA3FF]' : 'text-[#7C89AD]'">{{ item.tag }}</div>
    <div>
      <div class="font-serif font-600 text-lg text-[#F3F6FC]">{{ item.title }}</div>
      <div class="text-sm text-[#93A2C4] mt-1">{{ item.desc }}</div>
    </div>
  </div>
</div>

<div v-click="3" class="mt-6 font-mono text-xs text-[#4DA3FF]">
  ↗ Chang et al. (2023, PHCRS) tune hybrid weights with a genetic algorithm; Subha et al. (2023) use deep hybrid CNN+LSTM models
</div>

</div>

---

<div class="portal-rail"></div>

<div class="h-full flex flex-col justify-center pl-28 pr-20">

<div class="font-mono text-xs tracking-[0.35em] text-[#4DA3FF] mb-3">§ 02 — RELATED WORK</div>
<h1 class="font-serif font-700 uppercase text-4xl text-[#F3F6FC] mb-10">The Research Gap</h1>

<div class="space-y-4 max-w-2xl text-lg text-[#D6DEF0]">
<v-clicks>

- Studies mostly split into **two separate tracks** — either service integration, or recommendation algorithms
- Portal-integration studies (e.g. Reddii et al., 2026) rarely include an educational recommender
- Recommender studies (Chang et al., Subha et al.) are usually tested as a **standalone tool**, outside any unified portal
- **No study combines both** — a unified portal *and* a hybrid course recommender — grounded in a real Iranian university context

</v-clicks>
</div>

</div>

---
transition: slide-up
---

<div class="portal-rail"></div>

<div class="h-full flex flex-col justify-center pl-28 pr-20">

<div class="font-mono text-xs tracking-[0.35em] text-[#4DA3FF] mb-3">§ 03 — METHODOLOGY</div>
<h1 class="font-serif font-700 uppercase text-4xl text-[#F3F6FC] mb-2">Research Methodology</h1>
<div class="text-sm text-[#7C89AD] mb-10">Mixed-methods research design</div>

<div class="grid grid-cols-2 gap-6 max-w-4xl">

<v-click>
<div class="border border-[#212A4A] bg-[#0E1330] p-6">
  <div class="font-mono text-xs text-[#4DA3FF] mb-2">QUANTITATIVE</div>
  <div class="font-serif font-600 text-lg text-[#F3F6FC] mb-2">Registration Data Analysis</div>
  <div class="text-sm text-[#93A2C4]">Past course history and enrollment trends across several semesters, to spot patterns and give an early read on recommender performance</div>
</div>
</v-click>

<v-click>
<div class="border border-[#212A4A] bg-[#0E1330] p-6">
  <div class="font-mono text-xs text-[#4DA3FF] mb-2">QUALITATIVE</div>
  <div class="font-serif font-600 text-lg text-[#F3F6FC] mb-2">Semi-Structured Interviews</div>
  <div class="text-sm text-[#93A2C4]">With students and academic advisors, to surface real concerns and validate the portal's proposed requirements</div>
</div>
</v-click>

</div>

<v-click>
<div class="mt-8 font-mono text-xs text-[#93A2C4] max-w-2xl">
  Sampling: convenience sampling of recently active students for the quantitative part; purposive sampling (varied entry year, major, system usage) plus advisors for the qualitative part
</div>
</v-click>

</div>

---

<div class="portal-rail"></div>

<div class="h-full flex flex-col justify-center pl-28 pr-20">

<div class="font-mono text-xs tracking-[0.35em] text-[#4DA3FF] mb-3">§ 04 — SYSTEM ARCHITECTURE</div>
<h1 class="font-serif font-700 uppercase text-4xl text-[#F3F6FC] mb-8">Proposed Architecture</h1>

<div class="flex flex-col gap-2.5 max-w-3xl">
<div
  v-for="(layer, i) in [
    ['Student data', 'Secure store of academic history, GPA per subject, self-reported skills and interests'],
    ['Unified backend', 'REST API, SSO auth, and an internal service bus routing all six service domains'],
    ['Personalised frontend', 'A single-page React dashboard — schedule, finances, GPA, and course suggestions in one view'],
    ['Recommender engine', 'A separate Ranker + Scorer service returning ranked courses with a rationale tag'],
  ]"
  :key="i"
  v-motion
  :initial="{ x: -80, opacity: 0 }"
  :enter="{ x: 0, opacity: 1, transition: { delay: i * 280 } }"
  class="flex items-center gap-4 border-l-2 border-[#4DA3FF] bg-[#0E1330] pl-4 pr-5 py-3">
  <div class="font-mono text-xs text-[#4DA3FF] w-6 shrink-0">L{{ i + 1 }}</div>
  <div class="font-serif font-600 text-[#F3F6FC] w-48 shrink-0">{{ layer[0] }}</div>
  <div class="text-sm text-[#93A2C4]">{{ layer[1] }}</div>
</div>
</div>

<v-click at="5">
<div class="mt-6 font-mono text-xs text-[#7C89AD] max-w-2xl">
  Layers connect through a REST API and an internal service bus — independently scalable and replaceable
</div>
</v-click>

</div>

---

<div class="portal-rail"></div>

<div class="h-full flex flex-col justify-center pl-28 pr-20">

<div class="font-mono text-xs tracking-[0.35em] text-[#4DA3FF] mb-3">§ 04 — SYSTEM ARCHITECTURE</div>
<h1 class="font-serif font-700 uppercase text-4xl text-[#F3F6FC] mb-10">Six Service Domains</h1>

<div class="max-w-3xl border border-[#212A4A]">
<div v-for="(row, i) in [
    ['Registration', 'Browse, select, and manage courses with live seat counts and prerequisite checks'],
    ['Grades & transcript', 'Current grades, historical transcript, GPA trends by semester'],
    ['Finance & admin', 'Tuition invoices, online payment, loan requests, scholarship status'],
    ['Schedule & calendar', 'Interactive calendar — class schedule, exam dates, deadlines, campus events'],
    ['Academic advising', 'Book an advising slot, track its status, get responses inside the portal'],
    ['Centralized notices', 'Announcements from department, instructors, and finance in a single feed'],
  ]" :key="i"
  v-motion :initial="{ opacity: 0, x: -20 }" :enter="{ opacity: 1, x: 0, transition: { delay: i * 150 } }"
  class="grid grid-cols-[190px_1fr] gap-4 px-5 py-3" :class="i % 2 === 0 ? 'bg-[#0E1330]' : ''">
  <div class="font-mono text-xs text-[#4DA3FF] uppercase self-center">{{ row[0] }}</div>
  <div class="text-sm text-[#D6DEF0] self-center" v-html="row[1]"></div>
</div>
</div>

</div>

---
transition: fade
---

<div class="portal-rail"></div>

<div class="h-full flex flex-col justify-center pl-28 pr-20">

<div class="font-mono text-xs tracking-[0.35em] text-[#4DA3FF] mb-3">§ 05 — RECOMMENDER DESIGN</div>
<h1 class="font-serif font-700 uppercase text-4xl text-[#F3F6FC] mb-10">Hybrid Recommender Algorithm</h1>

<div class="grid grid-cols-2 gap-14">

<div class="text-lg text-[#D6DEF0] leading-relaxed">
A weighted blend of collaborative and content-based scores, so the system stays useful even with little history — then leans more on peer patterns as enrollment data accumulates.
</div>

<div class="space-y-6">
<v-click>
<div class="flex gap-4">
  <div class="font-mono text-[#4DA3FF] text-sm shrink-0">FEATURES</div>
  <div class="text-[#93A2C4] text-sm">Each student gets a vector of academic history, interests/goals, and skills; each course gets a vector of syllabus, prerequisites, and topic tags</div>
</div>
</v-click>
<v-click>
<div class="flex gap-4">
  <div class="font-mono text-[#4DA3FF] text-sm shrink-0">SCORE</div>
  <div class="text-[#93A2C4] text-sm">Score(i, j) = α · CF(i, j) + (1 − α) · CB(i, j) — α tuned dynamically, smaller for new students with little history</div>
</div>
</v-click>
<v-click>
<div class="flex gap-4">
  <div class="font-mono text-[#4DA3FF] text-sm shrink-0">RATIONALE</div>
  <div class="text-[#93A2C4] text-sm">Each suggested course carries a short reason tag — e.g. "matches your interest in AI" — to build trust and reduce the "black box" feeling</div>
</div>
</v-click>
</div>

</div>

</div>

---
transition: slide-up
---

<div class="portal-rail"></div>

<div class="h-full flex flex-col justify-center pl-28 pr-20">

<div class="font-mono text-xs tracking-[0.35em] text-[#4DA3FF] mb-3">§ 06 — IMPLEMENTATION</div>
<h1 class="font-serif font-700 uppercase text-4xl text-[#F3F6FC] mb-10">Proposed Technology Stack</h1>

<div class="grid grid-cols-2 gap-5 max-w-4xl">

<v-click><div class="border border-[#212A4A] bg-[#0E1330] p-5"><span class="font-mono text-[#4DA3FF] text-sm">01</span><div class="mt-2 text-[#D6DEF0]">Frontend — React / Next.js single-page, responsive dashboard</div></div></v-click>

<v-click><div class="border border-[#212A4A] bg-[#0E1330] p-5"><span class="font-mono text-[#4DA3FF] text-sm">02</span><div class="mt-2 text-[#D6DEF0]">Backend — Node.js with Express for the REST API and auth logic</div></div></v-click>

<v-click><div class="border border-[#212A4A] bg-[#0E1330] p-5"><span class="font-mono text-[#4DA3FF] text-sm">03</span><div class="mt-2 text-[#D6DEF0]">Database — relational store (MySQL / PostgreSQL) for structured student and course data</div></div></v-click>

<v-click><div class="border border-[#212A4A] bg-[#0E1330] p-5"><span class="font-mono text-[#4DA3FF] text-sm">04</span><div class="mt-2 text-[#D6DEF0]">Recommender — separate Python service, exposed through an internal API</div></div></v-click>

<v-click><div class="border border-[#212A4A] bg-[#0E1330] p-5"><span class="font-mono text-[#4DA3FF] text-sm">05</span><div class="mt-2 text-[#D6DEF0]">Auth — token-based single sign-on (JWT) across all six service domains</div></div></v-click>

<v-click><div class="border border-[#212A4A] bg-[#0E1330] p-5"><span class="font-mono text-[#4DA3FF] text-sm">06</span><div class="mt-2 text-[#D6DEF0]">Deployment — Docker containers for independent, scalable services</div></div></v-click>

</div>

</div>

---

<div class="portal-rail"></div>

<div class="h-full flex flex-col justify-center pl-28 pr-20">

<div class="font-mono text-xs tracking-[0.35em] text-[#4DA3FF] mb-3">§ 07 — EVALUATION</div>
<h1 class="font-serif font-700 uppercase text-4xl text-[#F3F6FC] mb-10">Evaluation &amp; Success Metrics</h1>

<div class="grid grid-cols-2 gap-10">

<div>
<div class="font-mono text-xs text-[#7C89AD] uppercase mb-3">Technical metrics</div>
<v-clicks>

- Response time for key actions — login, dashboard load, registration
- Recommender accuracy via Precision@k and Recall@k on a held-out test set
- System stability under concurrent load at peak times like registration

</v-clicks>
</div>

<div>
<div class="font-mono text-xs text-[#7C89AD] uppercase mb-3">User metrics</div>
<v-clicks>

- Student satisfaction with integration, pre/post prototype use
- Adoption rate — share of students taking at least one suggested course
- Drop in support tickets caused by cross-system confusion

</v-clicks>
</div>

</div>

</div>

---

<div class="portal-rail"></div>

<div class="h-full flex flex-col justify-center pl-28 pr-20">

<div class="font-mono text-xs tracking-[0.35em] text-[#4DA3FF] mb-3">§ 08 — PROTOTYPE</div>
<h1 class="font-serif font-700 uppercase text-4xl text-[#F3F6FC] mb-10">UI Prototype &amp; Expected Findings</h1>

<div class="grid grid-cols-2 gap-10">

<div>
<div class="font-mono text-xs text-[#7C89AD] uppercase mb-3">What the prototype shows</div>
<v-clicks>

- The problem — system fragmentation, visualized
- The six integrated service domains
- A sample dashboard: schedule, GPA, finances
- Suggested-course cards with match score and rationale

</v-clicks>
</div>

<div>
<div class="font-mono text-xs text-[#7C89AD] uppercase mb-3">Expected findings (hypotheses)</div>
<v-clicks>

- Most students use **four or more** systems — and call it a major time drain
- Hybrid recommender should outperform single-method models for **new students**
- A visible rationale tag should raise the **acceptance rate** of suggestions

</v-clicks>
</div>

</div>

<v-click at="7">
<div class="mt-8 font-mono text-xs text-[#FFB347] max-w-2xl">
  ⚠ Numbers shown in the prototype are mock data for demonstrating the interface — not results from real data collection
</div>
</v-click>

</div>

---

<div class="portal-rail"></div>

<div class="h-full flex flex-col justify-center pl-28 pr-20">

<div class="font-mono text-xs tracking-[0.35em] text-[#4DA3FF] mb-3">§ 09 — CONTRIBUTION</div>
<h1 class="font-serif font-700 uppercase text-4xl text-[#F3F6FC] mb-10">Innovation &amp; Distinction</h1>

<div class="space-y-4 max-w-2xl text-lg text-[#D6DEF0]">
<v-clicks>

- Unlike Reddii et al. (2026), which automates **administrative workflows only**, this work adds an educational recommender
- Unlike Chang et al. and Subha et al., whose recommenders are studied as **standalone tools**, this work embeds one inside a full portal
- Core contribution: treating the recommender not as a separate product, but as **one of six services**, with direct access to unified student data
- Grounded specifically in the context of **Iranian university systems** (Golestan and its satellites)

</v-clicks>
</div>

</div>

---

<div class="portal-rail"></div>

<div class="h-full flex flex-col justify-center pl-28 pr-20">

<div class="font-mono text-xs tracking-[0.35em] text-[#FFB347] mb-3">§ 10 — LIMITATIONS</div>
<h1 class="font-serif font-700 uppercase text-4xl text-[#F3F6FC] mb-10">Research Limitations</h1>

<div class="grid grid-cols-2 gap-3 max-w-4xl">

<v-click><div class="border-l-2 border-[#FFB347] bg-[#FFB347]/5 p-4"><div class="font-serif font-600 text-[#F3F6FC]">Data access</div><div class="text-sm text-[#93A2C4] mt-1">Real, full registration data usually needs institutional approval and privacy safeguards</div></div></v-click>

<v-click><div class="border-l-2 border-[#FFB347] bg-[#FFB347]/5 p-4"><div class="font-serif font-600 text-[#F3F6FC]">Legacy integration</div><div class="text-sm text-[#93A2C4] mt-1">Connecting to existing systems like Golestan needs IT-department cooperation and API access that may not be available</div></div></v-click>

<v-click><div class="border-l-2 border-[#FFB347] bg-[#FFB347]/5 p-4"><div class="font-serif font-600 text-[#F3F6FC]">Cold start</div><div class="text-sm text-[#93A2C4] mt-1">Still an open challenge for new students or new courses with no enrollment history</div></div></v-click>

<v-click><div class="border-l-2 border-[#FFB347] bg-[#FFB347]/5 p-4"><div class="font-serif font-600 text-[#F3F6FC]">Scope of this report</div><div class="text-sm text-[#93A2C4] mt-1">This report is a research and architecture design; full build and real user testing belong to the capstone project phase</div></div></v-click>

</div>

</div>

---
layout: center
class: text-center
---

<div class="max-w-3xl mx-auto">

<div class="font-mono text-xs tracking-[0.35em] text-[#4DA3FF] mb-4">§ 11 — CONCLUSION</div>
<h1 class="font-serif font-700 uppercase text-4xl text-[#F3F6FC] mb-10">Conclusion</h1>

<div class="space-y-4 text-lg text-[#D6DEF0] text-left">
<v-clicks>

- Fragmented university systems are a real, recurring pain point — in Iran and internationally
- A hybrid collaborative + content-based recommender is a balanced fit for a data-scarce university setting
- The proposed four-layer architecture unifies six service domains behind one login
- This report lays a research and architectural foundation for a fuller capstone prototype

</v-clicks>
</div>

</div>

---

<div class="portal-rail"></div>

<div class="h-full flex flex-col justify-center pl-28 pr-20">

<div class="font-mono text-xs tracking-[0.35em] text-[#4DA3FF] mb-3">§ 11 — CONCLUSION</div>
<h1 class="font-serif font-700 uppercase text-4xl text-[#F3F6FC] mb-10">Future Work</h1>

<div class="space-y-4 max-w-2xl text-lg text-[#D6DEF0]">
<v-clicks>

- Secure real registration and grade data, with proper anonymization and institutional approval
- Build and calibrate the recommender's α weighting on real enrollment history
- Integrate with existing university systems such as Golestan through available APIs
- Run a full user study measuring satisfaction, adoption rate, and cognitive load

</v-clicks>
</div>

</div>

---
layout: center
class: text-center
---

<div class="absolute inset-0 flex items-center justify-center pointer-events-none">
  <div class="relative w-[820px] h-[380px]">
    <div class="absolute top-0 left-0 w-14 h-14 border-t-2 border-l-2 border-[#4DA3FF]/60"></div>
    <div class="absolute top-0 right-0 w-14 h-14 border-t-2 border-r-2 border-[#4DA3FF]/60"></div>
    <div class="absolute bottom-0 left-0 w-14 h-14 border-b-2 border-l-2 border-[#4DA3FF]/60"></div>
    <div class="absolute bottom-0 right-0 w-14 h-14 border-b-2 border-r-2 border-[#4DA3FF]/60"></div>
  </div>
</div>

<div class="relative">
  <div class="font-mono text-xs tracking-[0.4em] text-[#4DA3FF] mb-6">END OF SESSION</div>
  <h1 class="font-serif font-700 uppercase text-5xl text-[#F3F6FC]">Thank You</h1>
  <div class="font-mono text-sm text-[#93A2C4] mt-6">Questions and feedback are welcome</div>
  <div class="flex items-center justify-center gap-3 my-8">
    <div class="w-16 h-px bg-[#4DA3FF]/50"></div>
    <div class="w-1.5 h-1.5 rounded-full bg-[#4DA3FF]"></div>
    <div class="w-16 h-px bg-[#4DA3FF]/50"></div>
  </div>
  <div class="font-mono text-xs text-[#7C89AD]">
        Alireza Hassani Eghtedar &nbsp;·&nbsp; Computer Engineering Capstone Project &nbsp;·&nbsp; Kharazmi University
  </div>
</div>

<style>
/*
  Signature element used across content slides: a vertical "portal node-line"
  rail — a spine of connected dots down the left margin, standing in for the
  many separate campus systems this project unifies. The HUD deck used a
  speed-tape rail (tick marks); this one intentionally uses nodes-on-a-line
  instead, since the subject here is "connecting systems," not "instruments."
*/
.portal-rail {
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  width: 56px;
  pointer-events: none;
  opacity: 0.55;
}
.portal-rail::before {
  content: '';
  position: absolute;
  left: 40px;
  top: 8%;
  bottom: 8%;
  width: 1px;
  background: linear-gradient(to bottom, transparent, rgba(77,163,255,0.35) 15%, rgba(77,163,255,0.35) 85%, transparent);
}
.portal-rail::after {
  content: '';
  position: absolute;
  left: 36px;
  top: 8%;
  bottom: 8%;
  width: 9px;
  background-image: radial-gradient(circle, rgba(77,163,255,0.55) 1.6px, transparent 1.6px);
  background-size: 9px 34px;
  background-repeat: repeat-y;
}
.slidev-layout {
  background-image: repeating-linear-gradient(to bottom, rgba(255,255,255,0.012) 0px, rgba(255,255,255,0.012) 1px, transparent 1px, transparent 3px);
}
</style>
