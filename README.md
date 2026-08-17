<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>VT DESIGNS — Creative Designer</title>

  <meta name="description"
        content="VT DESIGNS — Professional graphic designer creating modern, creative and memorable visual experiences.">

  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>

  <!-- Google Font -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">

  <!-- Icons -->
  <script src="https://unpkg.com/lucide@latest"></script>

  <style>

    * {
      scroll-behavior: smooth;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      background: #050505;
      color: white;
      overflow-x: hidden;
    }

    /* =========================
       CUSTOM SCROLLBAR
    ========================== */

    ::-webkit-scrollbar {
      width: 8px;
    }

    ::-webkit-scrollbar-track {
      background: #050505;
    }

    ::-webkit-scrollbar-thumb {
      background: #d4af37;
      border-radius: 20px;
    }

    /* =========================
       GOLD TEXT
    ========================== */

    .gold-text {
      background: linear-gradient(
        90deg,
        #f5d76e,
        #d4af37,
        #fff1a8,
        #d4af37
      );

      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    /* =========================
       NAVBAR
    ========================== */

    .navbar {
      backdrop-filter: blur(18px);
      -webkit-backdrop-filter: blur(18px);
      background: rgba(5, 5, 5, 0.72);
      border-bottom: 1px solid rgba(255,255,255,0.07);
    }

    /* =========================
       HERO
    ========================== */

    .hero-bg {
      background:
        radial-gradient(
          circle at 50% 30%,
          rgba(212,175,55,0.15),
          transparent 30%
        ),
        radial-gradient(
          circle at 10% 80%,
          rgba(212,175,55,0.08),
          transparent 30%
        ),
        #050505;
    }

    .hero-grid {
      background-image:
        linear-gradient(rgba(255,255,255,0.025) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,0.025) 1px, transparent 1px);

      background-size: 50px 50px;

      mask-image: linear-gradient(
        to bottom,
        black 30%,
        transparent 100%
      );
    }

    .profile-ring {
      position: relative;
    }

    .profile-ring::before {
      content: "";
      position: absolute;
      inset: -8px;

      border-radius: 50%;

      background: conic-gradient(
        from 0deg,
        #d4af37,
        transparent,
        #f5d76e,
        transparent,
        #d4af37
      );

      animation: rotateRing 7s linear infinite;
    }

    .profile-ring img {
      position: relative;
      z-index: 2;
    }

    @keyframes rotateRing {
      to {
        transform: rotate(360deg);
      }
    }

    /* =========================
       FLOATING BADGE
    ========================== */

    .floating-badge {
      animation: float 4s ease-in-out infinite;
    }

    @keyframes float {

      0%,100% {
        transform: translateY(0);
      }

      50% {
        transform: translateY(-10px);
      }

    }

    /* =========================
       GLASS CARD
    ========================== */

    .glass {
      background: rgba(255,255,255,0.035);
      border: 1px solid rgba(255,255,255,0.08);
      backdrop-filter: blur(15px);
      -webkit-backdrop-filter: blur(15px);
    }

    .glass:hover {
      border-color: rgba(212,175,55,0.35);
    }

    /* =========================
       PORTFOLIO
    ========================== */

    .portfolio-card {
      position: relative;
      overflow: hidden;
      border-radius: 20px;
      background: #111;
    }

    .portfolio-card img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: transform 0.7s ease;
    }

    .portfolio-card:hover img {
      transform: scale(1.08);
    }

    .portfolio-overlay {
      position: absolute;
      inset: 0;

      display: flex;
      align-items: flex-end;

      padding: 25px;

      background: linear-gradient(
        to top,
        rgba(0,0,0,0.9),
        rgba(0,0,0,0.1),
        transparent
      );

      opacity: 0;
      transition: 0.4s ease;
    }

    .portfolio-card:hover .portfolio-overlay {
      opacity: 1;
    }

    /* =========================
       SERVICE CARDS
    ========================== */

    .service-card {
      transition: all 0.35s ease;
    }

    .service-card:hover {
      transform: translateY(-8px);
      border-color: rgba(212,175,55,0.5);
      box-shadow: 0 20px 60px rgba(212,175,55,0.08);
    }

    .service-icon {
      transition: 0.35s ease;
    }

    .service-card:hover .service-icon {
      transform: scale(1.1) rotate(-5deg);
    }

    /* =========================
       BUTTONS
    ========================== */

    .gold-button {
      background: linear-gradient(
        135deg,
        #f5d76e,
        #d4af37
      );

      color: #050505;

      transition: all 0.3s ease;
    }

    .gold-button:hover {
      transform: translateY(-3px);
      box-shadow: 0 15px 35px rgba(212,175,55,0.25);
    }

    .outline-button {
      border: 1px solid rgba(212,175,55,0.6);
      color: #f5d76e;
      transition: 0.3s ease;
    }

    .outline-button:hover {
      background: #d4af37;
      color: #050505;
      transform: translateY(-3px);
    }

    /* =========================
       REVEAL ANIMATION
    ========================== */

    .reveal {
      opacity: 0;
      transform: translateY(40px);
      transition: all 0.8s ease;
    }

    .reveal.active {
      opacity: 1;
      transform: translateY(0);
    }

    /* =========================
       MOBILE MENU
    ========================== */

    #mobileMenu {
      transition: all 0.3s ease;
    }

    /* =========================
       TEXT ROTATION
    ========================== */

    .rotating-word {
      display: inline-block;
      min-width: 250px;
    }

    /* =========================
       GLOW
    ========================== */

    .gold-glow {
      box-shadow:
        0 0 80px rgba(212,175,55,0.08),
        inset 0 0 40px rgba(212,175,55,0.02);
    }

  </style>
</head>


<body>

<!-- ==========================================
     NAVBAR
=========================================== -->

<header class="navbar fixed top-0 left-0 w-full z-50">

  <nav class="max-w-7xl mx-auto px-5 lg:px-8">

    <div class="h-20 flex items-center justify-between">

      <!-- LOGO -->

      <a href="HOME.html" class="flex items-center gap-3">

        <div class="w-11 h-11 rounded-full overflow-hidden border border-yellow-500/60">
          <img
            src="Untitled designbb.png"
            alt="VT Designs Logo"
            class="w-full h-full object-cover"
          >
        </div>

        <div>
          <div class="font-black tracking-tight text-lg">
            VT <span class="text-yellow-400">DESIGNS</span>
          </div>

          <div class="text-[9px] tracking-[0.25em] text-gray-500 uppercase">
            Your vision is our design
          </div>
        </div>

      </a>


      <!-- DESKTOP MENU -->

      <div class="hidden md:flex items-center gap-9 text-sm font-medium">

        <a href="#home"
           class="text-yellow-400">
          Home
        </a>

        <a href="ABOUT.html"
           class="text-gray-400 hover:text-white transition">
          About
        </a>

        <a href="#services"
           class="text-gray-400 hover:text-white transition">
          Services
        </a>

        <a href="#portfolio"
           class="text-gray-400 hover:text-white transition">
          Portfolio
        </a>

        <a href="CONTACT US.html"
           class="text-gray-400 hover:text-white transition">
          Contact
        </a>

      </div>


      <!-- DESKTOP CTA -->

      <a
        href="CONTACT US.html"
        class="hidden md:flex gold-button px-5 py-2.5 rounded-full font-bold text-sm items-center gap-2"
      >
        Let's Work
        <i data-lucide="arrow-up-right" class="w-4 h-4"></i>
      </a>


      <!-- MOBILE BUTTON -->

      <button
        id="menuButton"
        class="md:hidden w-11 h-11 glass rounded-full flex items-center justify-center"
        onclick="toggleMenu()"
      >

        <i data-lucide="menu" id="menuIcon"></i>

      </button>

    </div>

  </nav>


  <!-- MOBILE MENU -->

  <div
    id="mobileMenu"
    class="hidden md:hidden border-t border-white/10 bg-black/95"
  >

    <div class="px-5 py-5 space-y-2">

      <a href="#home"
         onclick="toggleMenu()"
         class="block px-4 py-3 rounded-xl hover:bg-white/5">
        Home
      </a>

      <a href="ABOUT.html"
         class="block px-4 py-3 rounded-xl hover:bg-white/5">
        About
      </a>

      <a href="#services"
         onclick="toggleMenu()"
         class="block px-4 py-3 rounded-xl hover:bg-white/5">
        Services
      </a>

      <a href="#portfolio"
         onclick="toggleMenu()"
         class="block px-4 py-3 rounded-xl hover:bg-white/5">
        Portfolio
      </a>

      <a href="CONTACT US.html"
         class="block px-4 py-3 rounded-xl hover:bg-white/5">
        Contact
      </a>

    </div>

  </div>

</header>


<!-- ==========================================
     HERO
=========================================== -->

<section
  id="home"
  class="hero-bg min-h-screen relative flex items-center pt-28 overflow-hidden"
>

  <div class="hero-grid absolute inset-0"></div>


  <!-- Background glow -->

  <div class="absolute w-[500px] h-[500px] bg-yellow-500/5 rounded-full blur-3xl top-20 right-0"></div>

  <div class="absolute w-[400px] h-[400px] bg-yellow-500/5 rounded-full blur-3xl bottom-0 left-0"></div>


  <div class="max-w-7xl mx-auto px-5 lg:px-8 w-full relative z-10">

    <div class="grid lg:grid-cols-2 gap-16 items-center">


      <!-- LEFT -->

      <div class="reveal">

        <div class="inline-flex items-center gap-2 glass rounded-full px-4 py-2 mb-7">

          <span class="w-2 h-2 bg-green-400 rounded-full animate-pulse"></span>

          <span class="text-xs uppercase tracking-[0.18em] text-gray-300">
            Available for projects
          </span>

        </div>


        <h1 class="text-5xl sm:text-6xl lg:text-7xl font-black leading-[1.05] tracking-tight">

          I turn ideas

          <br>

          into

          <span class="gold-text">
            visuals.
          </span>

        </h1>


        <p class="mt-7 text-gray-400 text-base sm:text-lg leading-8 max-w-xl">

          I'm <strong class="text-white">VT DESIGN</strong>,
          a creative designer focused on creating bold,
          modern and memorable designs that help brands
          stand out.

        </p>


        <!-- Rotating text -->

        <div class="mt-5 text-sm text-gray-500">

          Currently

          <span class="text-yellow-400 font-semibold rotating-word">
            creating identities
          </span>

        </div>


        <!-- BUTTONS -->

        <div class="flex flex-wrap gap-4 mt-9">

          <a
            href="#portfolio"
            class="gold-button px-7 py-3.5 rounded-full font-bold flex items-center gap-2"
          >

            View My Work

            <i data-lucide="arrow-down" class="w-4 h-4"></i>

          </a>


          <a
            href="CONTACT US.html"
            class="outline-button px-7 py-3.5 rounded-full font-bold flex items-center gap-2"
          >

            Hire Me

            <i data-lucide="arrow-up-right" class="w-4 h-4"></i>

          </a>

        </div>


        <!-- SOCIALS -->

        <div class="flex items-center gap-5 mt-10">

          <span class="text-xs text-gray-600 uppercase tracking-widest">
            Follow
          </span>

          <a href="#" class="text-gray-500 hover:text-yellow-400 transition">
            <i data-lucide="instagram" class="w-5 h-5"></i>
          </a>

          <a href="#" class="text-gray-500 hover:text-yellow-400 transition">
            <i data-lucide="facebook" class="w-5 h-5"></i>
          </a>

          <a href="#" class="text-gray-500 hover:text-yellow-400 transition">
            <i data-lucide="linkedin" class="w-5 h-5"></i>
          </a>

        </div>

      </div>


      <!-- RIGHT -->

      <div class="flex justify-center lg:justify-end reveal">

        <div class="relative">


          <!-- Decorative circle -->

          <div class="absolute -inset-12 rounded-full border border-yellow-500/10"></div>

          <div class="absolute -inset-20 rounded-full border border-yellow-500/5"></div>


          <!-- Image -->

          <div class="profile-ring w-64 h-64 sm:w-80 sm:h-80">

            <div class="relative w-full h-full rounded-full bg-black p-2">

              <img
                src="Untitled designbb.png"
                alt="VT Design"
                class="w-full h-full object-cover rounded-full"
              >

            </div>

          </div>


          <!-- Badge -->

          <div
            class="floating-badge absolute -bottom-3 -left-8 glass rounded-2xl px-5 py-4"
          >

            <div class="flex items-center gap-3">

              <div class="w-10 h-10 rounded-xl bg-yellow-500/10 flex items-center justify-center">

                <i data-lucide="palette" class="text-yellow-400"></i>

              </div>

              <div>

                <p class="font-bold text-sm">
                  Creative Designer
                </p>

                <p class="text-xs text-gray-500">
                  Graphics • Branding • UI
                </p>

              </div>

            </div>

          </div>


          <!-- Experience badge -->

          <div
            class="floating-badge absolute -top-5 -right-8 glass rounded-2xl px-5 py-4"
            style="animation-delay:1s"
          >

            <p class="text-2xl font-black gold-text">
              100%
            </p>

            <p class="text-xs text-gray-500">
              Passion
            </p>

          </div>

        </div>

      </div>

    </div>


    <!-- Scroll -->

    <div class="hidden md:flex justify-center mt-20">

      <a
        href="#about"
        class="flex flex-col items-center gap-2 text-gray-600 hover:text-yellow-400 transition"
      >

        <span class="text-[10px] uppercase tracking-[0.3em]">
          Scroll to explore
        </span>

        <i data-lucide="mouse" class="w-5 h-5"></i>

      </a>

    </div>

  </div>

</section>


<!-- ==========================================
     STATS
=========================================== -->

<section class="border-y border-white/5 bg-[#080808]">

  <div class="max-w-7xl mx-auto px-5 lg:px-8">

    <div class="grid grid-cols-2 md:grid-cols-4">

      <div class="py-10 text-center border-r border-white/5 reveal">

        <div class="text-3xl font-black gold-text">
          50+
        </div>

        <p class="text-xs text-gray-500 mt-2 uppercase tracking-widest">
          Designs Created
        </p>

      </div>


      <div class="py-10 text-center md:border-r border-white/5 reveal">

        <div class="text-3xl font-black gold-text">
          20+
        </div>

        <p class="text-xs text-gray-500 mt-2 uppercase tracking-widest">
          Happy Clients
        </p>

      </div>


      <div class="py-10 text-center border-r border-white/5 reveal">

        <div class="text-3xl font-black gold-text">
          10+
        </div>

        <p class="text-xs text-gray-500 mt-2 uppercase tracking-widest">
          Projects
        </p>

      </div>


      <div class="py-10 text-center reveal">

        <div class="text-3xl font-black gold-text">
          24/7
        </div>

        <p class="text-xs text-gray-500 mt-2 uppercase tracking-widest">
          Creativity
        </p>

      </div>

    </div>

  </div>

</section>


<!-- ==========================================
     ABOUT
=========================================== -->

<section id="about" class="py-28">

  <div class="max-w-7xl mx-auto px-5 lg:px-8">

    <div class="grid lg:grid-cols-2 gap-16 items-center">


      <div class="reveal">

        <p class="text-yellow-400 text-xs uppercase tracking-[0.3em] font-bold mb-4">
          About Me
        </p>

        <h2 class="text-4xl sm:text-5xl font-black leading-tight">
          Design is more than
          <span class="gold-text">
            making things beautiful.
          </span>
        </h2>

      </div>


      <div class="reveal">

        <p class="text-gray-400 leading-8">

          I believe great design should communicate,
          connect and leave an impression.

          From social media graphics and promotional
          materials to brand visuals and digital experiences,
          I combine creativity with strategy to create designs
          that actually serve a purpose.

        </p>

        <a
          href="ABOUT.html"
          class="inline-flex items-center gap-2 mt-7 text-yellow-400 font-semibold hover:gap-4 transition-all"
        >

          More about me

          <i data-lucide="arrow-right" class="w-4 h-4"></i>

        </a>

      </div>

    </div>

  </div>

</section>


<!-- ==========================================
     SERVICES
=========================================== -->

<section id="services" class="py-28 bg-[#080808]">

  <div class="max-w-7xl mx-auto px-5 lg:px-8">

    <div class="text-center max-w-2xl mx-auto reveal">

      <p class="text-yellow-400 text-xs uppercase tracking-[0.3em] font-bold mb-4">
        What I Do
      </p>

      <h2 class="text-4xl sm:text-5xl font-black">
        Creative services
        <span class="gold-text">
          built for you.
        </span>
      </h2>

      <p class="text-gray-500 mt-5 leading-7">
        From concept to final design, I create visuals
        that make your brand look professional.
      </p>

    </div>


    <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-5 mt-16">


      <!-- SERVICE -->

      <div class="service-card glass rounded-3xl p-7 reveal">

        <div class="service-icon w-14 h-14 rounded-2xl bg-yellow-500/10 flex items-center justify-center">

          <i data-lucide="pen-tool" class="text-yellow-400 w-6 h-6"></i>

        </div>

        <h3 class="font-bold text-xl mt-7">
          Graphic Design
        </h3>

        <p class="text-gray-500 text-sm leading-7 mt-3">
          Social media graphics, flyers, posters,
          banners and promotional materials.
        </p>

      </div>


      <!-- SERVICE -->

      <div class="service-card glass rounded-3xl p-7 reveal">

        <div class="service-icon w-14 h-14 rounded-2xl bg-yellow-500/10 flex items-center justify-center">

          <i data-lucide="sparkles" class="text-yellow-400 w-6 h-6"></i>

        </div>

        <h3 class="font-bold text-xl mt-7">
          Brand Identity
        </h3>

        <p class="text-gray-500 text-sm leading-7 mt-3">
          Logos and visual identities that help
          businesses establish a memorable presence.
        </p>

      </div>


      <!-- SERVICE -->

      <div class="service-card glass rounded-3xl p-7 reveal">

        <div class="service-icon w-14 h-14 rounded-2xl bg-yellow-500/10 flex items-center justify-center">

          <i data-lucide="layout" class="text-yellow-400 w-6 h-6"></i>

        </div>

        <h3 class="font-bold text-xl mt-7">
          UI / UX Design
        </h3>

        <p class="text-gray-500 text-sm leading-7 mt-3">
          Clean and intuitive interfaces designed
          to create better digital experiences.
        </p>

      </div>


      <!-- SERVICE -->

      <div class="service-card glass rounded-3xl p-7 reveal">

        <div class="service-icon w-14 h-14 rounded-2xl bg-yellow-500/10 flex items-center justify-center">

          <i data-lucide="monitor-smartphone" class="text-yellow-400 w-6 h-6"></i>

        </div>

        <h3 class="font-bold text-xl mt-7">
          Web Design
        </h3>

        <p class="text-gray-500 text-sm leading-7 mt-3">
          Modern responsive websites designed to
          showcase brands and convert visitors.
        </p>

      </div>

    </div>

  </div>

</section>


<!-- ==========================================
     PORTFOLIO
=========================================== -->

<section id="portfolio" class="py-28">

  <div class="max-w-7xl mx-auto px-5 lg:px-8">


    <div class="flex flex-col md:flex-row md:items-end justify-between gap-5 reveal">

      <div>

        <p class="text-yellow-400 text-xs uppercase tracking-[0.3em] font-bold mb-4">
          Selected Work
        </p>

        <h2 class="text-4xl sm:text-5xl font-black">
          My latest
          <span class="gold-text">
            creations.
          </span>
        </h2>

      </div>


      <a
        href="#"
        class="text-sm text-gray-400 hover:text-yellow-400 transition flex items-center gap-2"
      >

        View all projects

        <i data-lucide="arrow-up-right" class="w-4 h-4"></i>

      </a>

    </div>


    <!-- PORTFOLIO GRID -->

    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-5 mt-14">


      <div class="portfolio-card h-[430px] reveal">

        <img src="Designs 1.jpg" alt="VT Design Project">

        <div class="portfolio-overlay">

          <div>

            <span class="text-yellow-400 text-xs uppercase tracking-widest">
              Graphic Design
            </span>

            <h3 class="text-xl font-bold mt-1">
              Creative Campaign
            </h3>

          </div>

        </div>

      </div>


      <div class="portfolio-card h-[430px] reveal">

        <img src="Designs 2.jpg" alt="VT Design Project">

        <div class="portfolio-overlay">

          <div>

            <span class="text-yellow-400 text-xs uppercase tracking-widest">
              Branding
            </span>

            <h3 class="text-xl font-bold mt-1">
              Visual Identity
            </h3>

          </div>

        </div>

      </div>


      <div class="portfolio-card h-[430px] reveal">

        <img src="Design 3.jpg" alt="VT Design Project">

        <div class="portfolio-overlay">

          <div>

            <span class="text-yellow-400 text-xs uppercase tracking-widest">
              Social Media
            </span>

            <h3 class="text-xl font-bold mt-1">
              Social Campaign
            </h3>

          </div>

        </div>

      </div>


      <div class="portfolio-card h-[430px] reveal">

        <img src="Design 4.jpg" alt="VT Design Project">

        <div class="portfolio-overlay">

          <div>

            <span class="text-yellow-400 text-xs uppercase tracking-widest">
              Design
            </span>

            <h3 class="text-xl font-bold mt-1">
              Promotional Design
            </h3>

          </div>

        </div>

      </div>


      <div class="portfolio-card h-[430px] reveal">

        <img src="Design 5.jpg" alt="VT Design Project">

        <div class="portfolio-overlay">

          <div>

            <span class="text-yellow-400 text-xs uppercase tracking-widest">
              Creative
            </span>

            <h3 class="text-xl font-bold mt-1">
              Digital Artwork
            </h3>

          </div>

        </div>

      </div>


      <div class="portfolio-card h-[430px] reveal">

        <img src="Design 6.jpg" alt="VT Design Project">

        <div class="portfolio-overlay">

          <div>

            <span class="text-yellow-400 text-xs uppercase tracking-widest">
              Campaign
            </span>

            <h3 class="text-xl font-bold mt-1">
              Brand Promotion
            </h3>

          </div>

        </div>

      </div>

    </div>

  </div>

</section>


<!-- ==========================================
     PROCESS
=========================================== -->

<section class="py-28 bg-[#080808]">

  <div class="max-w-7xl mx-auto px-5 lg:px-8">


    <div class="max-w-2xl reveal">

      <p class="text-yellow-400 text-xs uppercase tracking-[0.3em] font-bold mb-4">
        My Process
      </p>

      <h2 class="text-4xl sm:text-5xl font-black">
        From idea to
        <span class="gold-text">
          final design.
        </span>
      </h2>

    </div>


    <div class="grid md:grid-cols-3 gap-5 mt-14">


      <div class="glass rounded-3xl p-8 reveal">

        <span class="text-yellow-400 text-sm font-bold">
          01
        </span>

        <h3 class="text-2xl font-bold mt-8">
          Discover
        </h3>

        <p class="text-gray-500 leading-7 mt-3">
          We discuss your idea, goals, audience
          and the message you want your design
          to communicate.
        </p>

      </div>


      <div class="glass rounded-3xl p-8 reveal">

        <span class="text-yellow-400 text-sm font-bold">
          02
        </span>

        <h3 class="text-2xl font-bold mt-8">
          Design
        </h3>

        <p class="text-gray-500 leading-7 mt-3">
          I transform the concept into a polished
          visual solution with attention to detail
          and creativity.
        </p>

      </div>


      <div class="glass rounded-3xl p-8 reveal">

        <span class="text-yellow-400 text-sm font-bold">
          03
        </span>

        <h3 class="text-2xl font-bold mt-8">
          Deliver
        </h3>

        <p class="text-gray-500 leading-7 mt-3">
          After revisions and final approval,
          you receive the completed design ready
          for use.
        </p>

      </div>

    </div>

  </div>

</section>


<!-- ==========================================
     WHY VT DESIGNS
=========================================== -->

<section class="py-28">

  <div class="max-w-7xl mx-auto px-5 lg:px-8">


    <div class="grid lg:grid-cols-2 gap-14 items-center">


      <div class="reveal">

        <p class="text-yellow-400 text-xs uppercase tracking-[0.3em] font-bold mb-4">
          Why VT Designs
        </p>

        <h2 class="text-4xl sm:text-5xl font-black leading-tight">
          Creativity with
          <span class="gold-text">
            purpose.
          </span>
        </h2>

        <p class="text-gray-500 leading-8 mt-6">
          You don't just need a design.
          You need something that communicates
          your message and makes people stop,
          look and remember.
        </p>

      </div>


      <div class="grid sm:grid-cols-2 gap-4 reveal">


        <div class="glass rounded-2xl p-6">

          <i data-lucide="lightbulb"
             class="text-yellow-400 w-6 h-6">
          </i>

          <h3 class="font-bold mt-5">
            Creative Thinking
          </h3>

          <p class="text-gray-500 text-sm mt-2">
            Fresh concepts built around your idea.
          </p>

        </div>


        <div class="glass rounded-2xl p-6">

          <i data-lucide="zap"
             class="text-yellow-400 w-6 h-6">
          </i>

          <h3 class="font-bold mt-5">
            Fast Delivery
          </h3>

          <p class="text-gray-500 text-sm mt-2">
            Efficient workflow without sacrificing quality.
          </p>

        </div>


        <div class="glass rounded-2xl p-6">

          <i data-lucide="badge-check"
             class="text-yellow-400 w-6 h-6">
          </i>

          <h3 class="font-bold mt-5">
            Attention to Detail
          </h3>

          <p class="text-gray-500 text-sm mt-2">
            Every element gets the attention it deserves.
          </p>

        </div>


        <div class="glass rounded-2xl p-6">

          <i data-lucide="messages-square"
             class="text-yellow-400 w-6 h-6">
          </i>

          <h3 class="font-bold mt-5">
            Easy Communication
          </h3>

          <p class="text-gray-500 text-sm mt-2">
            Your feedback stays at the heart of the process.
          </p>

        </div>

      </div>

    </div>

  </div>

</section>


<!-- ==========================================
     CTA
=========================================== -->

<section class="py-20 px-5">

  <div class="max-w-6xl mx-auto">

    <div
      class="gold-glow relative overflow-hidden rounded-[2rem] border border-yellow-500/20 bg-gradient-to-br from-yellow-500/10 to-transparent p-10 sm:p-16 text-center reveal"
    >

      <div class="absolute w-72 h-72 bg-yellow-500/10 rounded-full blur-3xl -top-40 left-1/2 -translate-x-1/2"></div>


      <div class="relative">

        <p class="text-yellow-400 text-xs uppercase tracking-[0.3em] font-bold">
          Have a project?
        </p>

        <h2 class="text-4xl sm:text-6xl font-black mt-5">
          Let's create something
          <span class="gold-text">
            amazing.
          </span>
        </h2>

        <p class="text-gray-500 max-w-xl mx-auto mt-5 leading-7">
          Tell me what you have in mind and let's
          turn your idea into a design that stands out.
        </p>


        <a
          href="CONTACT US.html"
          class="inline-flex gold-button px-8 py-4 rounded-full font-bold mt-9 items-center gap-2"
        >

          Start a Project

          <i data-lucide="arrow-up-right" class="w-5 h-5"></i>

        </a>

      </div>

    </div>

  </div>

</section>


<!-- ==========================================
     FOOTER
=========================================== -->

<footer class="border-t border-white/5 bg-[#030303]">

  <div class="max-w-7xl mx-auto px-5 lg:px-8 py-14">


    <div class="grid md:grid-cols-3 gap-10">


      <!-- BRAND -->

      <div>

        <div class="flex items-center gap-3">

          <div class="w-10 h-10 rounded-full overflow-hidden border border-yellow-500/50">

            <img
              src="Untitled designbb.png"
              alt="VT Designs"
              class="w-full h-full object-cover"
            >

          </div>

          <span class="font-black">
            VT <span class="text-yellow-400">DESIGNS</span>
          </span>

        </div>

        <p class="text-gray-600 text-sm leading-7 mt-5 max-w-sm">
          Turning ideas, dreams and visions into
          stunning visual experiences.
        </p>

      </div>


      <!-- NAVIGATION -->

      <div>

        <h3 class="font-bold text-sm uppercase tracking-widest">
          Navigation
        </h3>

        <div class="space-y-3 mt-5 text-sm text-gray-500">

          <a href="#home"
             class="block hover:text-yellow-400 transition">
            Home
          </a>

          <a href="ABOUT.html"
             class="block hover:text-yellow-400 transition">
            About
          </a>

          <a href="#services"
             class="block hover:text-yellow-400 transition">
            Services
          </a>

          <a href="#portfolio"
             class="block hover:text-yellow-400 transition">
            Portfolio
          </a>

          <a href="CONTACT US.html"
             class="block hover:text-yellow-400 transition">
            Contact
          </a>

        </div>

      </div>


      <!-- CONTACT -->

      <div>

        <h3 class="font-bold text-sm uppercase tracking-widest">
          Let's Connect
        </h3>

        <p class="text-gray-600 text-sm mt-5 leading-7">
          Ready to bring your next idea to life?
        </p>

        <a
          href="CONTACT US.html"
          class="inline-flex items-center gap-2 text-yellow-400 font-semibold text-sm mt-4"
        >

          Contact Me

          <i data-lucide="arrow-up-right" class="w-4 h-4"></i>

        </a>

      </div>

    </div>


    <div class="border-t border-white/5 mt-12 pt-7 flex flex-col sm:flex-row justify-between gap-4 text-xs text-gray-600">

      <p>
        © 2026 VT DESIGNS. All Rights Reserved.
      </p>

      <p>
        Designed & Built by VT DESIGNS
      </p>

    </div>

  </div>

</footer>


<!-- ==========================================
     JAVASCRIPT
=========================================== -->

<script>

  /* =========================
     LUCIDE ICONS
  ========================== */

  lucide.createIcons();


  /* =========================
     MOBILE MENU
  ========================== */

  function toggleMenu() {

    const menu = document.getElementById("mobileMenu");

    menu.classList.toggle("hidden");

  }


  /* =========================
     SCROLL REVEAL
  ========================== */

  const revealElements =
    document.querySelectorAll(".reveal");


  const observer =
    new IntersectionObserver(
      (entries) => {

        entries.forEach(entry => {

          if (entry.isIntersecting) {

            entry.target.classList.add("active");

            observer.unobserve(entry.target);

          }

        });

      },
      {
        threshold: 0.12
      }
    );


  revealElements.forEach(element => {

    observer.observe(element);

  });


  /* =========================
     ROTATING HERO TEXT
  ========================== */

  const rotatingWord =
    document.querySelector(".rotating-word");


  const words = [

    "creating identities",

    "designing experiences",

    "building brands",

    "creating visuals",

    "bringing ideas to life"

  ];


  let currentWord = 0;


  setInterval(() => {

    rotatingWord.style.opacity = "0";

    rotatingWord.style.transform = "translateY(5px)";


    setTimeout(() => {

      currentWord =
        (currentWord + 1) % words.length;

      rotatingWord.textContent =
        words[currentWord];

      rotatingWord.style.opacity = "1";

      rotatingWord.style.transform =
        "translateY(0)";

    }, 250);

  }, 2500);


  /* =========================
     ACTIVE NAVIGATION
  ========================== */

  const sections =
    document.querySelectorAll("section[id]");

  const navLinks =
    document.querySelectorAll("header nav a");


  window.addEventListener("scroll", () => {

    let current = "";


    sections.forEach(section => {

      const sectionTop =
        section.offsetTop - 150;

      if (window.scrollY >= sectionTop) {

        current =
          section.getAttribute("id");

      }

    });


    navLinks.forEach(link => {

      link.classList.remove(
        "text-yellow-400"
      );

    });

  });


</script>

</body>
</html>
