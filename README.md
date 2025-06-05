<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>DSpace Bhutan - Learn. Grow. Inspire.</title>
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Pacifico&display=swap"
      rel="stylesheet"
    />
    <link
      href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Poppins:wght@300;400;500;600;700&display=swap"
      rel="stylesheet"
    />
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/remixicon/4.6.0/remixicon.min.css"
    />
    <script src="https://cdn.tailwindcss.com/3.4.16"></script>
    <script>
      tailwind.config = {
        theme: {
          extend: {
            colors: { primary: "#6366f1", secondary: "#4f46e5" },
            borderRadius: {
              none: "0px",
              sm: "4px",
              DEFAULT: "8px",
              md: "12px",
              lg: "16px",
              xl: "20px",
              "2xl": "24px",
              "3xl": "32px",
              full: "9999px",
              button: "8px",
            },
          },
        },
      };
    </script>
    <style>
      :where([class^="ri-"])::before { content: "\f3c2"; }
      body {
          font-family: 'Inter', sans-serif;
          scroll-behavior: smooth;
      }
      .hero-section {
          background-position: center;
          background-size: cover;
          background-repeat: no-repeat;
      }
      .gradient-overlay {
          background: linear-gradient(90deg, rgba(255,255,255,0.95) 0%, rgba(255,255,255,0.85) 50%, rgba(255,255,255,0) 100%);
      }
      .card-hover {
          transition: transform 0.3s ease, box-shadow 0.3s ease;
      }
      .card-hover:hover {
          transform: translateY(-5px);
          box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.1);
      }
      .theme-toggle:checked ~ .dot {
          transform: translateX(28px);
      }
      .nav-link {
          position: relative;
      }
      .nav-link::after {
          content: '';
          position: absolute;
          width: 0;
          height: 2px;
          bottom: -2px;
          left: 0;
          background-color: #6366f1;
          transition: width 0.3s ease;
      }
      .nav-link:hover::after, .nav-link.active::after {
          width: 100%;
      }
      .chatbot-container {
          transition: all 0.3s ease;
      }
      .search-input:focus {
          box-shadow: 0 0 0 2px rgba(99, 102, 241, 0.2);
      }
      input[type="range"]::-webkit-slider-thumb {
          -webkit-appearance: none;
          appearance: none;
          width: 18px;
          height: 18px;
          border-radius: 50%;
          background: #6366f1;
          cursor: pointer;
      }
      .custom-checkbox:checked + .checkbox-icon {
          background-color: #6366f1;
          border-color: #6366f1;
      }
      .custom-checkbox:checked + .checkbox-icon:after {
          content: '';
          position: absolute;
          left: 7px;
          top: 3px;
          width: 6px;
          height: 12px;
          border: solid white;
          border-width: 0 2px 2px 0;
          transform: rotate(45deg);
      }
      .custom-switch:checked + .switch-slider {
          background-color: #6366f1;
      }
      .custom-switch:checked + .switch-slider:before {
          transform: translateX(20px);
      }
      .tab-button.active {
          color: #6366f1;
          border-color: #6366f1;
      }
      .language-dropdown {
          max-height: 0;
          overflow: hidden;
          transition: max-height 0.3s ease;
      }
      .language-dropdown.open {
          max-height: 200px;
      }
      .fade-in {
          animation: fadeIn 0.5s ease-in-out;
      }
      @keyframes fadeIn {
          from { opacity: 0; transform: translateY(10px); }
          to { opacity: 1; transform: translateY(0); }
      }
    </style>
  </head>
  <body class="bg-gray-50 min-h-screen">
    <!-- Header -->
    <header class="fixed top-0 left-0 right-0 bg-white shadow-sm z-50">
      <div
        class="container mx-auto px-4 py-3 flex items-center justify-between"
      >
        <!-- Logo -->
        <div class="flex items-center space-x-2">
          <span class="text-2xl font-['Pacifico'] text-primary">DSpace</span>
          <span class="text-lg font-semibold">Bhutan</span>
        </div>

        <!-- Desktop Navigation -->
        <nav class="hidden md:flex items-center space-x-8">
          <a
            href="#home"
            class="nav-link active text-gray-800 hover:text-primary transition-colors"
            >Home</a
          >
          <a
            href="#knowledge-hub"
            class="nav-link text-gray-800 hover:text-primary transition-colors"
            >Knowledge Hub</a
          >
          <a
            href="#tech-tips"
            class="nav-link text-gray-800 hover:text-primary transition-colors"
            >Tech Tips</a
          >
          <a
            href="#motivation"
            class="nav-link text-gray-800 hover:text-primary transition-colors"
            >Dream Series</a
          >
          <a
            href="#solutions"
            class="nav-link text-gray-800 hover:text-primary transition-colors"
            >Solutions</a
          >
          <a
            href="#about"
            class="nav-link text-gray-800 hover:text-primary transition-colors"
            >About</a
          >
        </nav>

        <!-- Right Side Actions -->
        <div class="flex items-center space-x-4">
          <!-- Search -->
          <div class="relative hidden md:block">
            <input
              type="text"
              placeholder="Search..."
              class="search-input w-40 py-2 pl-8 pr-2 rounded-full text-sm border border-gray-200 focus:outline-none focus:border-primary transition-all"
            />
            <div
              class="absolute left-2 top-1/2 transform -translate-y-1/2 w-5 h-5 flex items-center justify-center text-gray-400"
            >
              <i class="ri-search-line"></i>
            </div>
          </div>

          <!-- Language Toggle -->
          <div class="relative">
            <button
              id="language-toggle"
              class="flex items-center space-x-1 text-sm text-gray-700 hover:text-primary transition-colors"
            >
              <div class="w-5 h-5 flex items-center justify-center">
                <i class="ri-global-line"></i>
              </div>
              <span class="hidden md:inline">EN</span>
              <div class="w-4 h-4 flex items-center justify-center">
                <i class="ri-arrow-down-s-line"></i>
              </div>
            </button>
            <div
              id="language-dropdown"
              class="language-dropdown absolute right-0 mt-2 w-28 bg-white rounded-md shadow-lg py-1 z-10"
            >
              <a
                href="#"
                class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100"
                >English</a
              >
              <a
                href="#"
                class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100"
                >Dzongkha</a
              >
            </div>
          </div>

          <!-- Theme Toggle -->
          <div class="hidden md:flex items-center">
            <label for="theme-toggle" class="flex items-center cursor-pointer">
              <div class="relative">
                <input
                  type="checkbox"
                  id="theme-toggle"
                  class="theme-toggle sr-only"
                />
                <div class="w-12 h-6 bg-gray-200 rounded-full"></div>
                <div
                  class="dot absolute left-1 top-1 bg-white w-4 h-4 rounded-full transition"
                ></div>
              </div>
              <div
                class="ml-2 w-5 h-5 flex items-center justify-center text-gray-600"
              >
                <i class="ri-moon-line"></i>
              </div>
            </label>
          </div>

          <!-- User Account -->
          <button
            class="w-9 h-9 flex items-center justify-center rounded-full bg-gray-100 hover:bg-gray-200 transition-colors"
          >
            <i class="ri-user-line text-gray-700"></i>
          </button>

          <!-- Mobile Menu Toggle -->
          <button
            id="mobile-menu-toggle"
            class="md:hidden w-9 h-9 flex items-center justify-center rounded-full bg-gray-100 hover:bg-gray-200 transition-colors"
          >
            <i class="ri-menu-line text-gray-700"></i>
          </button>
        </div>
      </div>

      <!-- Mobile Navigation Menu -->
      <div
        id="mobile-menu"
        class="hidden md:hidden bg-white border-t border-gray-100 py-2"
      >
        <nav class="container mx-auto px-4 flex flex-col space-y-3">
          <a
            href="#home"
            class="py-2 text-gray-800 hover:text-primary transition-colors"
            >Home</a
          >
          <a
            href="#knowledge-hub"
            class="py-2 text-gray-800 hover:text-primary transition-colors"
            >Knowledge Hub</a
          >
          <a
            href="#tech-tips"
            class="py-2 text-gray-800 hover:text-primary transition-colors"
            >Tech Tips</a
          >
          <a
            href="#motivation"
            class="py-2 text-gray-800 hover:text-primary transition-colors"
            >Dream Series</a
          >
          <a
            href="#solutions"
            class="py-2 text-gray-800 hover:text-primary transition-colors"
            >Solutions</a
          >
          <a
            href="#about"
            class="py-2 text-gray-800 hover:text-primary transition-colors"
            >About</a
          >
          <div
            class="pt-2 border-t border-gray-100 flex items-center justify-between"
          >
            <div class="flex items-center">
              <div
                class="w-5 h-5 flex items-center justify-center text-gray-600 mr-2"
              >
                <i class="ri-moon-line"></i>
              </div>
              <span class="text-sm text-gray-600">Dark Mode</span>
            </div>
            <label class="flex items-center cursor-pointer">
              <div class="relative">
                <input type="checkbox" class="theme-toggle sr-only" />
                <div class="w-12 h-6 bg-gray-200 rounded-full"></div>
                <div
                  class="dot absolute left-1 top-1 bg-white w-4 h-4 rounded-full transition"
                ></div>
              </div>
            </label>
          </div>
        </nav>
      </div>
    </header>

    <!-- Main Content -->
    <main class="pt-16">
      <!-- Hero Section -->
      <section
        id="home"
        class="hero-section relative"
        style="background-image: url('https://readdy.ai/api/search-image?query=futuristic%2520educational%2520technology%2520scene%2520with%2520Bhutanese%2520cultural%2520elements%252C%2520showing%2520digital%2520learning%2520tools%2520and%2520traditional%2520Bhutanese%2520architecture%2520elements%252C%2520with%2520mountains%2520in%2520background%252C%2520soft%2520lighting%252C%2520professional%2520photography%252C%2520clean%2520composition&width=1920&height=1080&seq=hero1&orientation=landscape');"
      >
        <div class="gradient-overlay w-full h-full">
          <div
            class="container mx-auto px-4 py-24 md:py-32 flex flex-col md:flex-row items-center"
          >
            <div class="w-full md:w-1/2 mb-10 md:mb-0">
              <h1
                class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 mb-6"
              >
                Learn. Grow. Inspire
                <span class="block text-primary">with DSpace Bhutan.</span>
              </h1>
              <p class="text-lg text-gray-700 mb-8 max-w-lg">
                Empowering Bhutanese youth with digital education, tech skills,
                and inspiration in both Dzongkha and English. Join Kinley
                Penjor's vision for a digitally connected Bhutan.
              </p>
              <div class="flex flex-wrap gap-4">
                <a
                  href="#knowledge-hub"
                  class="px-8 py-3 bg-primary text-white font-medium rounded-button hover:bg-indigo-600 transition-colors shadow-md hover:shadow-lg whitespace-nowrap"
                >
                  Start Learning
                </a>
                <a
                  href="#about"
                  class="px-8 py-3 bg-white text-primary font-medium rounded-button border border-primary hover:bg-gray-50 transition-colors whitespace-nowrap"
                >
                  Learn More
                </a>
              </div>
            </div>
          </div>
        </div>
        <!-- Scroll Indicator -->
        <div
          class="absolute bottom-8 left-1/2 transform -translate-x-1/2 flex flex-col items-center animate-bounce"
        >
          <span class="text-sm text-gray-600 mb-2">Scroll Down</span>
          <div class="w-8 h-8 flex items-center justify-center text-primary">
            <i class="ri-arrow-down-line"></i>
          </div>
        </div>
      </section>

      <!-- Main Navigation Cards -->
      <section class="py-16 bg-white">
        <div class="container mx-auto px-4">
          <h2 class="text-3xl font-bold text-center mb-12">
            Explore Our Digital Space
          </h2>

          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
            <!-- Knowledge Hub Card -->
            <div
              class="card-hover bg-white rounded-lg shadow-md overflow-hidden border border-gray-100"
            >
              <div class="h-48 bg-gray-100 relative">
                <img
                  src="https://readdy.ai/api/search-image?query=educational%2520content%2520with%2520books%252C%2520digital%2520tablets%2520and%2520learning%2520materials%2520arranged%2520neatly%2520on%2520a%2520desk%252C%2520soft%2520natural%2520lighting%252C%2520clean%2520minimal%2520background%252C%2520professional%2520photography&width=600&height=400&seq=khub1&orientation=landscape"
                  alt="Knowledge Hub"
                  class="w-full h-full object-cover object-top"
                />
              </div>
              <div class="p-6">
                <div
                  class="w-10 h-10 flex items-center justify-center rounded-full bg-indigo-100 text-primary mb-4"
                >
                  <i class="ri-book-open-line text-xl"></i>
                </div>
                <h3 class="text-xl font-semibold mb-2">Knowledge Hub</h3>
                <p class="text-gray-600 mb-4">
                  Access curriculum-based content, ICT tutorials, social studies
                  notes, and economic concepts.
                </p>
                <a
                  href="#knowledge-hub"
                  class="text-primary font-medium flex items-center"
                >
                  Explore Resources
                  <div class="w-5 h-5 flex items-center justify-center ml-1">
                    <i class="ri-arrow-right-line"></i>
                  </div>
                </a>
              </div>
            </div>

            <!-- Tech Tips Card -->
            <div
              class="card-hover bg-white rounded-lg shadow-md overflow-hidden border border-gray-100"
            >
              <div class="h-48 bg-gray-100 relative">
                <img
                  src="https://readdy.ai/api/search-image?query=tech%2520gadgets%2520and%2520devices%2520including%2520smartphone%252C%2520laptop%252C%2520tablet%2520arranged%2520on%2520a%2520clean%2520desk%2520with%2520minimal%2520accessories%252C%2520soft%2520lighting%252C%2520professional%2520product%2520photography%252C%2520clean%2520background&width=600&height=400&seq=tech1&orientation=landscape"
                  alt="Tech Tips"
                  class="w-full h-full object-cover object-top"
                />
              </div>
              <div class="p-6">
                <div
                  class="w-10 h-10 flex items-center justify-center rounded-full bg-indigo-100 text-primary mb-4"
                >
                  <i class="ri-device-line text-xl"></i>
                </div>
                <h3 class="text-xl font-semibold mb-2">Tech Tips</h3>
                <p class="text-gray-600 mb-4">
                  Discover practical tips for Windows, Android, productivity
                  tools, and AI applications.
                </p>
                <a
                  href="#tech-tips"
                  class="text-primary font-medium flex items-center"
                >
                  Watch Tutorials
                  <div class="w-5 h-5 flex items-center justify-center ml-1">
                    <i class="ri-arrow-right-line"></i>
                  </div>
                </a>
              </div>
            </div>

            <!-- Dream Series Card -->
            <div
              class="card-hover bg-white rounded-lg shadow-md overflow-hidden border border-gray-100"
            >
              <div class="h-48 bg-gray-100 relative">
                <img
                  src="https://readdy.ai/api/search-image?query=inspirational%2520scene%2520with%2520Bhutanese%2520mountains%2520at%2520sunrise%252C%2520person%2520meditating%2520or%2520looking%2520at%2520view%252C%2520peaceful%2520atmosphere%252C%2520motivational%2520setting%252C%2520professional%2520photography%252C%2520clean%2520composition&width=600&height=400&seq=dream1&orientation=landscape"
                  alt="Dream Series"
                  class="w-full h-full object-cover object-top"
                />
              </div>
              <div class="p-6">
                <div
                  class="w-10 h-10 flex items-center justify-center rounded-full bg-indigo-100 text-primary mb-4"
                >
                  <i class="ri-emotion-happy-line text-xl"></i>
                </div>
                <h3 class="text-xl font-semibold mb-2">Dream Series</h3>
                <p class="text-gray-600 mb-4">
                  Get inspired with motivational videos, success stories, and
                  personal development content.
                </p>
                <a
                  href="#motivation"
                  class="text-primary font-medium flex items-center"
                >
                  Find Inspiration
                  <div class="w-5 h-5 flex items-center justify-center ml-1">
                    <i class="ri-arrow-right-line"></i>
                  </div>
                </a>
              </div>
            </div>

            <!-- Student Solutions Card -->
            <div
              class="card-hover bg-white rounded-lg shadow-md overflow-hidden border border-gray-100"
            >
              <div class="h-48 bg-gray-100 relative">
                <img
                  src="https://readdy.ai/api/search-image?query=students%2520studying%2520together%2520in%2520a%2520modern%2520classroom%2520or%2520library%252C%2520helping%2520each%2520other%2520with%2520assignments%252C%2520Bhutanese%2520students%2520in%2520uniform%252C%2520educational%2520setting%252C%2520bright%2520natural%2520lighting%252C%2520professional%2520photography&width=600&height=400&seq=sol1&orientation=landscape"
                  alt="Student Solutions"
                  class="w-full h-full object-cover object-top"
                />
              </div>
              <div class="p-6">
                <div
                  class="w-10 h-10 flex items-center justify-center rounded-full bg-indigo-100 text-primary mb-4"
                >
                  <i class="ri-question-answer-line text-xl"></i>
                </div>
                <h3 class="text-xl font-semibold mb-2">Student Solutions</h3>
                <p class="text-gray-600 mb-4">
                  Access past paper solutions, get homework help, and connect
                  with our AI assistant.
                </p>
                <a
                  href="#solutions"
                  class="text-primary font-medium flex items-center"
                >
                  Get Help
                  <div class="w-5 h-5 flex items-center justify-center ml-1">
                    <i class="ri-arrow-right-line"></i>
                  </div>
                </a>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Knowledge Hub Section -->
      <section id="knowledge-hub" class="py-16 bg-gray-50">
        <div class="container mx-auto px-4">
          <div class="max-w-3xl mx-auto text-center mb-12">
            <h2 class="text-3xl font-bold mb-4">Knowledge Hub</h2>
            <p class="text-gray-600">
              Comprehensive educational resources aligned with the Bhutanese
              curriculum, covering various subjects and topics for students from
              classes 4 to 10.
            </p>
          </div>

          <!-- Filter Controls -->
          <div class="flex flex-wrap items-center justify-between mb-8">
            <div class="flex flex-wrap items-center gap-4 mb-4 md:mb-0">
              <span class="text-gray-700 font-medium">Filter by:</span>
              <div class="flex rounded-full bg-white shadow-sm p-1">
                <button
                  class="px-4 py-2 text-sm font-medium rounded-full bg-primary text-white whitespace-nowrap"
                >
                  All
                </button>
                <button
                  class="px-4 py-2 text-sm font-medium rounded-full text-gray-700 hover:bg-gray-100 whitespace-nowrap"
                >
                  ICT
                </button>
                <button
                  class="px-4 py-2 text-sm font-medium rounded-full text-gray-700 hover:bg-gray-100 whitespace-nowrap"
                >
                  Social Studies
                </button>
                <button
                  class="px-4 py-2 text-sm font-medium rounded-full text-gray-700 hover:bg-gray-100 whitespace-nowrap"
                >
                  Economics
                </button>
              </div>
            </div>

            <div class="flex items-center gap-4">
              <span class="text-gray-700 font-medium">Class Level:</span>
              <select
                class="bg-white border border-gray-200 rounded-lg py-2 px-3 pr-8 text-gray-700 focus:outline-none focus:border-primary"
              >
                <option>All Classes</option>
                <option>Class 4</option>
                <option>Class 5</option>
                <option>Class 6</option>
                <option>Class 7</option>
                <option>Class 8</option>
                <option>Class 9</option>
                <option>Class 10</option>
              </select>
            </div>
          </div>

          <!-- Content Grid -->
          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
            <!-- ICT Tutorial Card -->
            <div
              class="bg-white rounded-lg shadow-sm overflow-hidden border border-gray-100"
            >
              <div class="h-48 bg-gray-100 relative">
                <img
                  src="https://readdy.ai/api/search-image?query=computer%2520classroom%2520with%2520students%2520learning%2520programming%2520or%2520digital%2520skills%252C%2520screens%2520showing%2520code%252C%2520educational%2520setting%252C%2520clean%2520modern%2520classroom%252C%2520professional%2520photography&width=600&height=400&seq=ict1&orientation=landscape"
                  alt="ICT Basics"
                  class="w-full h-full object-cover object-top"
                />
                <div
                  class="absolute top-3 right-3 bg-indigo-100 text-primary text-xs font-medium px-2 py-1 rounded"
                >
                  ICT
                </div>
              </div>
              <div class="p-6">
                <h3 class="text-xl font-semibold mb-2">
                  Introduction to Programming
                </h3>
                <p class="text-gray-600 mb-4">
                  Learn the basics of programming with simple examples and
                  hands-on exercises suitable for beginners.
                </p>
                <div class="flex items-center justify-between">
                  <span class="text-sm text-gray-500">Class 7-10</span>
                  <div class="flex items-center text-sm text-gray-500">
                    <div class="w-4 h-4 flex items-center justify-center mr-1">
                      <i class="ri-time-line"></i>
                    </div>
                    <span>45 minutes</span>
                  </div>
                </div>
              </div>
            </div>

            <!-- Social Studies Card -->
            <div
              class="bg-white rounded-lg shadow-sm overflow-hidden border border-gray-100"
            >
              <div class="h-48 bg-gray-100 relative">
                <img
                  src="https://readdy.ai/api/search-image?query=traditional%2520Bhutanese%2520architecture%2520and%2520cultural%2520landmarks%252C%2520dzongs%2520and%2520temples%252C%2520beautiful%2520landscape%252C%2520professional%2520photography%2520with%2520clear%2520details%252C%2520educational%2520context%252C%2520clean%2520composition&width=600&height=400&seq=social1&orientation=landscape"
                  alt="Bhutanese History"
                  class="w-full h-full object-cover object-top"
                />
                <div
                  class="absolute top-3 right-3 bg-indigo-100 text-primary text-xs font-medium px-2 py-1 rounded"
                >
                  Social Studies
                </div>
              </div>
              <div class="p-6">
                <h3 class="text-xl font-semibold mb-2">
                  Bhutanese Cultural Heritage
                </h3>
                <p class="text-gray-600 mb-4">
                  Explore the rich cultural heritage of Bhutan, including
                  traditions, festivals, and historical landmarks.
                </p>
                <div class="flex items-center justify-between">
                  <span class="text-sm text-gray-500">Class 4-8</span>
                  <div class="flex items-center text-sm text-gray-500">
                    <div class="w-4 h-4 flex items-center justify-center mr-1">
                      <i class="ri-file-list-line"></i>
                    </div>
                    <span>12 lessons</span>
                  </div>
                </div>
              </div>
            </div>

            <!-- Economics Card -->
            <div
              class="bg-white rounded-lg shadow-sm overflow-hidden border border-gray-100"
            >
              <div class="h-48 bg-gray-100 relative">
                <img
                  src="https://readdy.ai/api/search-image?query=economic%2520concepts%2520visualization%2520with%2520charts%252C%2520graphs%252C%2520and%2520financial%2520elements%252C%2520clean%2520professional%2520business%2520setting%252C%2520educational%2520context%252C%2520minimal%2520clean%2520background%252C%2520professional%2520photography&width=600&height=400&seq=econ1&orientation=landscape"
                  alt="Economics Basics"
                  class="w-full h-full object-cover object-top"
                />
                <div
                  class="absolute top-3 right-3 bg-indigo-100 text-primary text-xs font-medium px-2 py-1 rounded"
                >
                  Economics
                </div>
              </div>
              <div class="p-6">
                <h3 class="text-xl font-semibold mb-2">
                  Basic Economic Principles
                </h3>
                <p class="text-gray-600 mb-4">
                  Understand fundamental economic concepts like supply and
                  demand, market structures, and GDP.
                </p>
                <div class="flex items-center justify-between">
                  <span class="text-sm text-gray-500">Class 9-10</span>
                  <div class="flex items-center text-sm text-gray-500">
                    <div class="w-4 h-4 flex items-center justify-center mr-1">
                      <i class="ri-video-line"></i>
                    </div>
                    <span>8 videos</span>
                  </div>
                </div>
              </div>
            </div>

            <!-- ICT Advanced Card -->
            <div
              class="bg-white rounded-lg shadow-sm overflow-hidden border border-gray-100"
            >
              <div class="h-48 bg-gray-100 relative">
                <img
                  src="https://readdy.ai/api/search-image?query=student%2520working%2520on%2520computer%2520with%2520spreadsheet%2520software%252C%2520data%2520analysis%252C%2520educational%2520setting%252C%2520clean%2520desk%2520with%2520computer%2520screen%2520showing%2520excel%2520or%2520similar%2520software%252C%2520professional%2520photography&width=600&height=400&seq=ict2&orientation=landscape"
                  alt="Spreadsheet Skills"
                  class="w-full h-full object-cover object-top"
                />
                <div
                  class="absolute top-3 right-3 bg-indigo-100 text-primary text-xs font-medium px-2 py-1 rounded"
                >
                  ICT
                </div>
              </div>
              <div class="p-6">
                <h3 class="text-xl font-semibold mb-2">Spreadsheet Mastery</h3>
                <p class="text-gray-600 mb-4">
                  Learn to use spreadsheet software for data analysis,
                  calculations, and creating visual representations.
                </p>
                <div class="flex items-center justify-between">
                  <span class="text-sm text-gray-500">Class 8-10</span>
                  <div class="flex items-center text-sm text-gray-500">
                    <div class="w-4 h-4 flex items-center justify-center mr-1">
                      <i class="ri-time-line"></i>
                    </div>
                    <span>60 minutes</span>
                  </div>
                </div>
              </div>
            </div>

            <!-- Social Studies History Card -->
            <div
              class="bg-white rounded-lg shadow-sm overflow-hidden border border-gray-100"
            >
              <div class="h-48 bg-gray-100 relative">
                <img
                  src="https://readdy.ai/api/search-image?query=historical%2520Bhutanese%2520scene%2520with%2520traditional%2520clothing%252C%2520historical%2520figures%2520or%2520events%2520depicted%252C%2520educational%2520context%252C%2520clean%2520composition%252C%2520professional%2520photography%2520or%2520high%2520quality%2520illustration&width=600&height=400&seq=hist1&orientation=landscape"
                  alt="Bhutanese History"
                  class="w-full h-full object-cover object-top"
                />
                <div
                  class="absolute top-3 right-3 bg-indigo-100 text-primary text-xs font-medium px-2 py-1 rounded"
                >
                  Social Studies
                </div>
              </div>
              <div class="p-6">
                <h3 class="text-xl font-semibold mb-2">
                  History of Modern Bhutan
                </h3>
                <p class="text-gray-600 mb-4">
                  Discover the journey of Bhutan from a traditional monarchy to
                  a democratic constitutional monarchy.
                </p>
                <div class="flex items-center justify-between">
                  <span class="text-sm text-gray-500">Class 6-10</span>
                  <div class="flex items-center text-sm text-gray-500">
                    <div class="w-4 h-4 flex items-center justify-center mr-1">
                      <i class="ri-file-list-line"></i>
                    </div>
                    <span>10 lessons</span>
                  </div>
                </div>
              </div>
            </div>

            <!-- Economics Advanced Card -->
            <div
              class="bg-white rounded-lg shadow-sm overflow-hidden border border-gray-100"
            >
              <div class="h-48 bg-gray-100 relative">
                <img
                  src="https://readdy.ai/api/search-image?query=Bhutanese%2520marketplace%2520or%2520economic%2520activity%252C%2520local%2520business%2520or%2520trade%252C%2520people%2520engaged%2520in%2520commerce%252C%2520educational%2520context%252C%2520clean%2520composition%252C%2520professional%2520photography&width=600&height=400&seq=econ2&orientation=landscape"
                  alt="Bhutanese Economy"
                  class="w-full h-full object-cover object-top"
                />
                <div
                  class="absolute top-3 right-3 bg-indigo-100 text-primary text-xs font-medium px-2 py-1 rounded"
                >
                  Economics
                </div>
              </div>
              <div class="p-6">
                <h3 class="text-xl font-semibold mb-2">
                  Bhutan's Economic Development
                </h3>
                <p class="text-gray-600 mb-4">
                  Understand Bhutan's unique approach to economic development
                  through the lens of Gross National Happiness.
                </p>
                <div class="flex items-center justify-between">
                  <span class="text-sm text-gray-500">Class 9-10</span>
                  <div class="flex items-center text-sm text-gray-500">
                    <div class="w-4 h-4 flex items-center justify-center mr-1">
                      <i class="ri-video-line"></i>
                    </div>
                    <span>6 videos</span>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- Load More Button -->
          <div class="text-center mt-10">
            <button
              class="px-6 py-3 bg-white text-primary font-medium rounded-button border border-primary hover:bg-gray-50 transition-colors shadow-sm whitespace-nowrap"
            >
              Load More Resources
            </button>
          </div>
        </div>
      </section>
      <!-- Tech Tips Section -->
      <section id="tech-tips" class="py-16 bg-white">
        <div class="container mx-auto px-4">
          <div class="max-w-3xl mx-auto text-center mb-12">
            <h2 class="text-3xl font-bold mb-4">Tech Tips & Tutorials</h2>
            <p class="text-gray-600">
              Practical guides and video tutorials to help you master technology
              tools, boost productivity, and solve common tech problems.
            </p>
          </div>

          <!-- Filter Tags -->
          <div class="flex flex-wrap justify-center gap-2 mb-10">
            <button
              class="px-4 py-2 bg-primary text-white text-sm font-medium rounded-full whitespace-nowrap"
            >
              All Tips
            </button>
            <button
              class="px-4 py-2 bg-white text-gray-700 text-sm font-medium rounded-full border border-gray-200 hover:bg-gray-50 whitespace-nowrap"
            >
              Windows
            </button>
            <button
              class="px-4 py-2 bg-white text-gray-700 text-sm font-medium rounded-full border border-gray-200 hover:bg-gray-50 whitespace-nowrap"
            >
              Android
            </button>
            <button
              class="px-4 py-2 bg-white text-gray-700 text-sm font-medium rounded-full border border-gray-200 hover:bg-gray-50 whitespace-nowrap"
            >
              Productivity
            </button>
            <button
              class="px-4 py-2 bg-white text-gray-700 text-sm font-medium rounded-full border border-gray-200 hover:bg-gray-50 whitespace-nowrap"
            >
              AI Tools
            </button>
            <button
              class="px-4 py-2 bg-white text-gray-700 text-sm font-medium rounded-full border border-gray-200 hover:bg-gray-50 whitespace-nowrap"
            >
              Internet
            </button>
          </div>

          <!-- Video Grid -->
          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
            <!-- Video Card 1 -->
            <div
              class="bg-white rounded-lg shadow-sm overflow-hidden border border-gray-100"
            >
              <div class="h-48 bg-gray-100 relative group">
                <img
                  src="https://readdy.ai/api/search-image?query=person%2520using%2520windows%2520computer%252C%2520showing%2520productivity%2520features%252C%2520clean%2520desk%2520setup%252C%2520professional%2520photography%252C%2520educational%2520context%252C%2520tutorial%2520setting&width=600&height=400&seq=win1&orientation=landscape"
                  alt="Windows Tips"
                  class="w-full h-full object-cover object-top"
                />
                <div
                  class="absolute inset-0 bg-black bg-opacity-40 opacity-0 group-hover:opacity-100 flex items-center justify-center transition-opacity"
                >
                  <div
                    class="w-16 h-16 flex items-center justify-center rounded-full bg-white bg-opacity-80 text-primary"
                  >
                    <i class="ri-play-fill text-3xl"></i>
                  </div>
                </div>
                <div
                  class="absolute top-3 right-3 bg-gray-900 bg-opacity-70 text-white text-xs font-medium px-2 py-1 rounded"
                >
                  8:24
                </div>
              </div>
              <div class="p-6">
                <div class="flex items-center gap-2 mb-3">
                  <span
                    class="px-2 py-1 bg-blue-100 text-blue-700 text-xs font-medium rounded"
                    >Windows</span
                  >
                  <span
                    class="px-2 py-1 bg-purple-100 text-purple-700 text-xs font-medium rounded"
                    >Productivity</span
                  >
                </div>
                <h3 class="text-xl font-semibold mb-2">
                  Windows 11 Hidden Features
                </h3>
                <p class="text-gray-600 mb-4">
                  Discover lesser-known features in Windows 11 that can boost
                  your productivity and enhance your experience.
                </p>
                <div class="flex items-center justify-between">
                  <div class="flex items-center">
                    <div
                      class="w-8 h-8 rounded-full bg-gray-200 flex items-center justify-center mr-2"
                    >
                      <i class="ri-user-line text-gray-600"></i>
                    </div>
                    <span class="text-sm text-gray-700">Kinley Penjor</span>
                  </div>
                  <span class="text-sm text-gray-500">June 2, 2025</span>
                </div>
              </div>
            </div>

            <!-- Video Card 2 -->
            <div
              class="bg-white rounded-lg shadow-sm overflow-hidden border border-gray-100"
            >
              <div class="h-48 bg-gray-100 relative group">
                <img
                  src="https://readdy.ai/api/search-image?query=person%2520using%2520smartphone%252C%2520android%2520device%2520with%2520app%2520demonstration%252C%2520educational%2520tutorial%2520setting%252C%2520clean%2520background%252C%2520professional%2520photography%252C%2520tech%2520tutorial%2520context&width=600&height=400&seq=android1&orientation=landscape"
                  alt="Android Tips"
                  class="w-full h-full object-cover object-top"
                />
                <div
                  class="absolute inset-0 bg-black bg-opacity-40 opacity-0 group-hover:opacity-100 flex items-center justify-center transition-opacity"
                >
                  <div
                    class="w-16 h-16 flex items-center justify-center rounded-full bg-white bg-opacity-80 text-primary"
                  >
                    <i class="ri-play-fill text-3xl"></i>
                  </div>
                </div>
                <div
                  class="absolute top-3 right-3 bg-gray-900 bg-opacity-70 text-white text-xs font-medium px-2 py-1 rounded"
                >
                  12:05
                </div>
              </div>
              <div class="p-6">
                <div class="flex items-center gap-2 mb-3">
                  <span
                    class="px-2 py-1 bg-green-100 text-green-700 text-xs font-medium rounded"
                    >Android</span
                  >
                </div>
                <h3 class="text-xl font-semibold mb-2">
                  Android Battery Optimization
                </h3>
                <p class="text-gray-600 mb-4">
                  Learn how to extend your Android phone's battery life with
                  these simple optimization techniques.
                </p>
                <div class="flex items-center justify-between">
                  <div class="flex items-center">
                    <div
                      class="w-8 h-8 rounded-full bg-gray-200 flex items-center justify-center mr-2"
                    >
                      <i class="ri-user-line text-gray-600"></i>
                    </div>
                    <span class="text-sm text-gray-700">Tshering Dorji</span>
                  </div>
                  <span class="text-sm text-gray-500">May 28, 2025</span>
                </div>
              </div>
            </div>

            <!-- Video Card 3 -->
            <div
              class="bg-white rounded-lg shadow-sm overflow-hidden border border-gray-100"
            >
              <div class="h-48 bg-gray-100 relative group">
                <img
                  src="https://readdy.ai/api/search-image?query=person%2520using%2520AI%2520tools%2520on%2520computer%252C%2520showing%2520AI%2520interface%2520or%2520application%252C%2520educational%2520setting%252C%2520clean%2520desk%2520with%2520modern%2520technology%252C%2520professional%2520photography%252C%2520tutorial%2520context&width=600&height=400&seq=ai1&orientation=landscape"
                  alt="AI Tools"
                  class="w-full h-full object-cover object-top"
                />
                <div
                  class="absolute inset-0 bg-black bg-opacity-40 opacity-0 group-hover:opacity-100 flex items-center justify-center transition-opacity"
                >
                  <div
                    class="w-16 h-16 flex items-center justify-center rounded-full bg-white bg-opacity-80 text-primary"
                  >
                    <i class="ri-play-fill text-3xl"></i>
                  </div>
                </div>
                <div
                  class="absolute top-3 right-3 bg-gray-900 bg-opacity-70 text-white text-xs font-medium px-2 py-1 rounded"
                >
                  15:37
                </div>
              </div>
              <div class="p-6">
                <div class="flex items-center gap-2 mb-3">
                  <span
                    class="px-2 py-1 bg-indigo-100 text-indigo-700 text-xs font-medium rounded"
                    >AI Tools</span
                  >
                  <span
                    class="px-2 py-1 bg-purple-100 text-purple-700 text-xs font-medium rounded"
                    >Productivity</span
                  >
                </div>
                <h3 class="text-xl font-semibold mb-2">
                  Getting Started with ChatGPT
                </h3>
                <p class="text-gray-600 mb-4">
                  A beginner's guide to using ChatGPT for school assignments,
                  creative writing, and problem-solving.
                </p>
                <div class="flex items-center justify-between">
                  <div class="flex items-center">
                    <div
                      class="w-8 h-8 rounded-full bg-gray-200 flex items-center justify-center mr-2"
                    >
                      <i class="ri-user-line text-gray-600"></i>
                    </div>
                    <span class="text-sm text-gray-700">Kinley Penjor</span>
                  </div>
                  <span class="text-sm text-gray-500">June 4, 2025</span>
                </div>
              </div>
            </div>

            <!-- Video Card 4 -->
            <div
              class="bg-white rounded-lg shadow-sm overflow-hidden border border-gray-100"
            >
              <div class="h-48 bg-gray-100 relative group">
                <img
                  src="https://readdy.ai/api/search-image?query=person%2520using%2520productivity%2520apps%2520on%2520computer%252C%2520time%2520management%2520software%252C%2520calendar%2520and%2520task%2520management%2520visible%252C%2520clean%2520desk%2520setup%252C%2520professional%2520photography%252C%2520educational%2520context&width=600&height=400&seq=prod1&orientation=landscape"
                  alt="Productivity Tips"
                  class="w-full h-full object-cover object-top"
                />
                <div
                  class="absolute inset-0 bg-black bg-opacity-40 opacity-0 group-hover:opacity-100 flex items-center justify-center transition-opacity"
                >
                  <div
                    class="w-16 h-16 flex items-center justify-center rounded-full bg-white bg-opacity-80 text-primary"
                  >
                    <i class="ri-play-fill text-3xl"></i>
                  </div>
                </div>
                <div
                  class="absolute top-3 right-3 bg-gray-900 bg-opacity-70 text-white text-xs font-medium px-2 py-1 rounded"
                >
                  10:42
                </div>
              </div>
              <div class="p-6">
                <div class="flex items-center gap-2 mb-3">
                  <span
                    class="px-2 py-1 bg-purple-100 text-purple-700 text-xs font-medium rounded"
                    >Productivity</span
                  >
                </div>
                <h3 class="text-xl font-semibold mb-2">
                  Time Management Apps for Students
                </h3>
                <p class="text-gray-600 mb-4">
                  Discover the best apps to help you manage your study schedule,
                  track assignments, and boost productivity.
                </p>
                <div class="flex items-center justify-between">
                  <div class="flex items-center">
                    <div
                      class="w-8 h-8 rounded-full bg-gray-200 flex items-center justify-center mr-2"
                    >
                      <i class="ri-user-line text-gray-600"></i>
                    </div>
                    <span class="text-sm text-gray-700">Deki Yangzom</span>
                  </div>
                  <span class="text-sm text-gray-500">May 30, 2025</span>
                </div>
              </div>
            </div>

            <!-- Video Card 5 -->
            <div
              class="bg-white rounded-lg shadow-sm overflow-hidden border border-gray-100"
            >
              <div class="h-48 bg-gray-100 relative group">
                <img
                  src="https://readdy.ai/api/search-image?query=person%2520using%2520internet%2520safely%252C%2520cybersecurity%2520concept%252C%2520password%2520protection%2520or%2520online%2520safety%2520visualization%252C%2520educational%2520context%252C%2520clean%2520composition%252C%2520professional%2520photography&width=600&height=400&seq=cyber1&orientation=landscape"
                  alt="Internet Safety"
                  class="w-full h-full object-cover object-top"
                />
                <div
                  class="absolute inset-0 bg-black bg-opacity-40 opacity-0 group-hover:opacity-100 flex items-center justify-center transition-opacity"
                >
                  <div
                    class="w-16 h-16 flex items-center justify-center rounded-full bg-white bg-opacity-80 text-primary"
                  >
                    <i class="ri-play-fill text-3xl"></i>
                  </div>
                </div>
                <div
                  class="absolute top-3 right-3 bg-gray-900 bg-opacity-70 text-white text-xs font-medium px-2 py-1 rounded"
                >
                  14:18
                </div>
              </div>
              <div class="p-6">
                <div class="flex items-center gap-2 mb-3">
                  <span
                    class="px-2 py-1 bg-red-100 text-red-700 text-xs font-medium rounded"
                    >Internet</span
                  >
                </div>
                <h3 class="text-xl font-semibold mb-2">
                  Internet Safety for Students
                </h3>
                <p class="text-gray-600 mb-4">
                  Essential tips for staying safe online, protecting your
                  privacy, and avoiding common internet scams.
                </p>
                <div class="flex items-center justify-between">
                  <div class="flex items-center">
                    <div
                      class="w-8 h-8 rounded-full bg-gray-200 flex items-center justify-center mr-2"
                    >
                      <i class="ri-user-line text-gray-600"></i>
                    </div>
                    <span class="text-sm text-gray-700">Kinley Penjor</span>
                  </div>
                  <span class="text-sm text-gray-500">May 25, 2025</span>
                </div>
              </div>
            </div>

            <!-- Video Card 6 -->
            <div
              class="bg-white rounded-lg shadow-sm overflow-hidden border border-gray-100"
            >
              <div class="h-48 bg-gray-100 relative group">
                <img
                  src="https://readdy.ai/api/search-image?query=person%2520using%2520windows%2520computer%2520showing%2520troubleshooting%2520or%2520system%2520settings%252C%2520educational%2520context%252C%2520clean%2520desk%2520setup%252C%2520professional%2520photography%252C%2520tutorial%2520setting&width=600&height=400&seq=win2&orientation=landscape"
                  alt="Windows Troubleshooting"
                  class="w-full h-full object-cover object-top"
                />
                <div
                  class="absolute inset-0 bg-black bg-opacity-40 opacity-0 group-hover:opacity-100 flex items-center justify-center transition-opacity"
                >
                  <div
                    class="w-16 h-16 flex items-center justify-center rounded-full bg-white bg-opacity-80 text-primary"
                  >
                    <i class="ri-play-fill text-3xl"></i>
                  </div>
                </div>
                <div
                  class="absolute top-3 right-3 bg-gray-900 bg-opacity-70 text-white text-xs font-medium px-2 py-1 rounded"
                >
                  11:53
                </div>
              </div>
              <div class="p-6">
                <div class="flex items-center gap-2 mb-3">
                  <span
                    class="px-2 py-1 bg-blue-100 text-blue-700 text-xs font-medium rounded"
                    >Windows</span
                  >
                </div>
                <h3 class="text-xl font-semibold mb-2">
                  Fixing Common Windows Problems
                </h3>
                <p class="text-gray-600 mb-4">
                  Step-by-step solutions for the most common Windows issues that
                  students encounter on their computers.
                </p>
                <div class="flex items-center justify-between">
                  <div class="flex items-center">
                    <div
                      class="w-8 h-8 rounded-full bg-gray-200 flex items-center justify-center mr-2"
                    >
                      <i class="ri-user-line text-gray-600"></i>
                    </div>
                    <span class="text-sm text-gray-700">Tshering Dorji</span>
                  </div>
                  <span class="text-sm text-gray-500">June 1, 2025</span>
                </div>
              </div>
            </div>
          </div>

          <!-- Submit Question Button -->
          <div class="mt-12 bg-indigo-50 rounded-lg p-8 text-center">
            <h3 class="text-xl font-semibold mb-3">Have a Tech Question?</h3>
            <p class="text-gray-600 mb-6 max-w-2xl mx-auto">
              Can't find what you're looking for? Submit your tech question and
              our team will create a tutorial to help you and others with
              similar issues.
            </p>
            <button
              class="px-8 py-3 bg-primary text-white font-medium rounded-button hover:bg-indigo-600 transition-colors shadow-md hover:shadow-lg whitespace-nowrap"
            >
              Submit a Question
            </button>
          </div>
        </div>
      </section>
      <!-- Motivation Section -->
      <section id="motivation" class="py-16 bg-gray-50">
        <div class="container mx-auto px-4">
          <div class="max-w-3xl mx-auto text-center mb-12">
            <h2 class="text-3xl font-bold mb-4">Dream Series & Motivation</h2>
            <p class="text-gray-600">
              Inspirational content to help you stay motivated, develop a
              positive mindset, and achieve your dreams and goals.
            </p>
          </div>

          <!-- Featured Video -->
          <div
            class="bg-white rounded-lg shadow-md overflow-hidden border border-gray-100 mb-12"
          >
            <div class="grid grid-cols-1 md:grid-cols-2">
              <div class="h-64 md:h-auto bg-gray-100 relative group">
                <img
                  src="https://readdy.ai/api/search-image?query=inspirational%2520Bhutanese%2520landscape%2520with%2520person%2520looking%2520at%2520mountain%2520view%252C%2520sunrise%2520or%2520sunset%252C%2520motivational%2520setting%252C%2520beautiful%2520natural%2520scenery%252C%2520professional%2520photography%252C%2520clean%2520composition&width=800&height=600&seq=motiv1&orientation=landscape"
                  alt="Dream Big"
                  class="w-full h-full object-cover object-top"
                />
                <div
                  class="absolute inset-0 bg-black bg-opacity-40 flex items-center justify-center"
                >
                  <div
                    class="w-20 h-20 flex items-center justify-center rounded-full bg-white bg-opacity-80 text-primary"
                  >
                    <i class="ri-play-fill text-4xl"></i>
                  </div>
                </div>
              </div>
              <div class="p-8">
                <div class="flex items-center gap-2 mb-4">
                  <span
                    class="px-2 py-1 bg-yellow-100 text-yellow-700 text-xs font-medium rounded"
                    >Featured</span
                  >
                  <span
                    class="px-2 py-1 bg-indigo-100 text-indigo-700 text-xs font-medium rounded"
                    >Motivation</span
                  >
                </div>
                <h3 class="text-2xl font-semibold mb-3">
                  Dream Big: Turning Challenges into Opportunities
                </h3>
                <p class="text-gray-600 mb-6">
                  An inspiring talk about how to overcome obstacles, develop
                  resilience, and transform challenges into stepping stones for
                  success.
                </p>
                <div class="flex items-center justify-between mb-6">
                  <div class="flex items-center">
                    <div
                      class="w-10 h-10 rounded-full bg-gray-200 flex items-center justify-center mr-3"
                    >
                      <i class="ri-user-line text-gray-600"></i>
                    </div>
                    <div>
                      <span class="block text-gray-800 font-medium"
                        >Kinley Penjor</span
                      >
                      <span class="text-sm text-gray-500"
                        >Founder, DSpace Bhutan</span
                      >
                    </div>
                  </div>
                  <span class="text-sm text-gray-500">18:24 mins</span>
                </div>
                <div class="flex items-center gap-6 text-gray-500">
                  <div class="flex items-center">
                    <div class="w-5 h-5 flex items-center justify-center mr-1">
                      <i class="ri-eye-line"></i>
                    </div>
                    <span>2,457 views</span>
                  </div>
                  <div class="flex items-center">
                    <div class="w-5 h-5 flex items-center justify-center mr-1">
                      <i class="ri-heart-line"></i>
                    </div>
                    <span>342 likes</span>
                  </div>
                  <div class="flex items-center">
                    <div class="w-5 h-5 flex items-center justify-center mr-1">
                      <i class="ri-chat-1-line"></i>
                    </div>
                    <span>48 comments</span>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- Motivation Videos Grid -->
          <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
            <!-- Motivation Video 1 -->
            <div
              class="bg-white rounded-lg shadow-sm overflow-hidden border border-gray-100"
            >
              <div class="h-48 bg-gray-100 relative group">
                <img
                  src="https://readdy.ai/api/search-image?query=student%2520studying%2520in%2520library%2520or%2520at%2520desk%252C%2520focused%2520and%2520determined%252C%2520educational%2520setting%252C%2520motivational%2520context%252C%2520clean%2520composition%252C%2520professional%2520photography&width=600&height=400&seq=study1&orientation=landscape"
                  alt="Study Motivation"
                  class="w-full h-full object-cover object-top"
                />
                <div
                  class="absolute inset-0 bg-black bg-opacity-40 opacity-0 group-hover:opacity-100 flex items-center justify-center transition-opacity"
                >
                  <div
                    class="w-16 h-16 flex items-center justify-center rounded-full bg-white bg-opacity-80 text-primary"
                  >
                    <i class="ri-play-fill text-3xl"></i>
                  </div>
                </div>
                <div
                  class="absolute top-3 right-3 bg-gray-900 bg-opacity-70 text-white text-xs font-medium px-2 py-1 rounded"
                >
                  5:42
                </div>
              </div>
              <div class="p-6">
                <h3 class="text-xl font-semibold mb-2">
                  5 Study Habits of Successful Students
                </h3>
                <p class="text-gray-600 mb-4">
                  Learn the effective study techniques that top students use to
                  excel in their academics.
                </p>
                <div class="flex items-center justify-between">
                  <div class="flex items-center text-sm text-gray-500">
                    <div class="w-4 h-4 flex items-center justify-center mr-1">
                      <i class="ri-eye-line"></i>
                    </div>
                    <span>1,245 views</span>
                  </div>
                  <div class="flex items-center text-sm text-gray-500">
                    <div class="w-4 h-4 flex items-center justify-center mr-1">
                      <i class="ri-heart-line"></i>
                    </div>
                    <span>186 likes</span>
                  </div>
                </div>
              </div>
            </div>

            <!-- Motivation Video 2 -->
            <div
              class="bg-white rounded-lg shadow-sm overflow-hidden border border-gray-100"
            >
              <div class="h-48 bg-gray-100 relative group">
                <img
                  src="https://readdy.ai/api/search-image?query=person%2520meditating%2520in%2520peaceful%2520Bhutanese%2520setting%252C%2520mountains%2520or%2520nature%2520background%252C%2520mindfulness%2520practice%252C%2520serene%2520atmosphere%252C%2520professional%2520photography%252C%2520clean%2520composition&width=600&height=400&seq=mind1&orientation=landscape"
                  alt="Mindfulness"
                  class="w-full h-full object-cover object-top"
                />
                <div
                  class="absolute inset-0 bg-black bg-opacity-40 opacity-0 group-hover:opacity-100 flex items-center justify-center transition-opacity"
                >
                  <div
                    class="w-16 h-16 flex items-center justify-center rounded-full bg-white bg-opacity-80 text-primary"
                  >
                    <i class="ri-play-fill text-3xl"></i>
                  </div>
                </div>
                <div
                  class="absolute top-3 right-3 bg-gray-900 bg-opacity-70 text-white text-xs font-medium px-2 py-1 rounded"
                >
                  8:15
                </div>
              </div>
              <div class="p-6">
                <h3 class="text-xl font-semibold mb-2">
                  Mindfulness for Academic Success
                </h3>
                <p class="text-gray-600 mb-4">
                  Discover how mindfulness practices can help reduce stress and
                  improve your focus and learning.
                </p>
                <div class="flex items-center justify-between">
                  <div class="flex items-center text-sm text-gray-500">
                    <div class="w-4 h-4 flex items-center justify-center mr-1">
                      <i class="ri-eye-line"></i>
                    </div>
                    <span>978 views</span>
                  </div>
                  <div class="flex items-center text-sm text-gray-500">
                    <div class="w-4 h-4 flex items-center justify-center mr-1">
                      <i class="ri-heart-line"></i>
                    </div>
                    <span>142 likes</span>
                  </div>
                </div>
              </div>
            </div>

            <!-- Motivation Video 3 -->
            <div
              class="bg-white rounded-lg shadow-sm overflow-hidden border border-gray-100"
            >
              <div class="h-48 bg-gray-100 relative group">
                <img
                  src="https://readdy.ai/api/search-image?query=successful%2520Bhutanese%2520professional%2520or%2520graduate%2520in%2520formal%2520attire%252C%2520achievement%2520or%2520success%2520concept%252C%2520educational%2520or%2520career%2520context%252C%2520professional%2520photography%252C%2520clean%2520composition&width=600&height=400&seq=success1&orientation=landscape"
                  alt="Career Success"
                  class="w-full h-full object-cover object-top"
                />
                <div
                  class="absolute inset-0 bg-black bg-opacity-40 opacity-0 group-hover:opacity-100 flex items-center justify-center transition-opacity"
                >
                  <div
                    class="w-16 h-16 flex items-center justify-center rounded-full bg-white bg-opacity-80 text-primary"
                  >
                    <i class="ri-play-fill text-3xl"></i>
                  </div>
                </div>
                <div
                  class="absolute top-3 right-3 bg-gray-900 bg-opacity-70 text-white text-xs font-medium px-2 py-1 rounded"
                >
                  12:37
                </div>
              </div>
              <div class="p-6">
                <h3 class="text-xl font-semibold mb-2">
                  From Student to Professional
                </h3>
                <p class="text-gray-600 mb-4">
                  Career advice and insights on transitioning from education to
                  professional life in Bhutan.
                </p>
                <div class="flex items-center justify-between">
                  <div class="flex items-center text-sm text-gray-500">
                    <div class="w-4 h-4 flex items-center justify-center mr-1">
                      <i class="ri-eye-line"></i>
                    </div>
                    <span>1,567 views</span>
                  </div>
                  <div class="flex items-center text-sm text-gray-500">
                    <div class="w-4 h-4 flex items-center justify-center mr-1">
                      <i class="ri-heart-line"></i>
                    </div>
                    <span>235 likes</span>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- Comment Section -->
          <div
            class="mt-12 bg-white rounded-lg shadow-sm p-8 border border-gray-100"
          >
            <h3 class="text-xl font-semibold mb-6">Share Your Thoughts</h3>

            <!-- Comment Form -->
            <div class="mb-8">
              <textarea
                placeholder="What inspired you today?"
                class="w-full p-4 border border-gray-200 rounded-lg focus:outline-none focus:border-primary transition-colors resize-none h-32"
              ></textarea>
              <div class="flex justify-end mt-4">
                <button
                  class="px-6 py-2 bg-primary text-white font-medium rounded-button hover:bg-indigo-600 transition-colors whitespace-nowrap"
                >
                  Post Comment
                </button>
              </div>
            </div>

            <!-- Comments List -->
            <div class="space-y-6">
              <!-- Comment 1 -->
              <div class="border-b border-gray-100 pb-6">
                <div class="flex items-start gap-4">
                  <div
                    class="w-10 h-10 rounded-full bg-gray-200 flex-shrink-0 flex items-center justify-center"
                  >
                    <i class="ri-user-line text-gray-600"></i>
                  </div>
                  <div class="flex-1">
                    <div class="flex items-center justify-between mb-2">
                      <div>
                        <span class="font-medium text-gray-800"
                          >Pema Wangchuk</span
                        >
                        <span class="text-sm text-gray-500 ml-2"
                          >3 days ago</span
                        >
                      </div>
                      <div class="flex items-center text-gray-500">
                        <div class="w-5 h-5 flex items-center justify-center">
                          <i class="ri-heart-line"></i>
                        </div>
                        <span class="text-sm ml-1">24</span>
                      </div>
                    </div>
                    <p class="text-gray-700">
                      The Dream Big video really resonated with me. As a student
                      from a remote village, I often face challenges with
                      internet connectivity and access to resources, but this
                      inspired me to find creative solutions. Thank you for the
                      motivation!
                    </p>
                  </div>
                </div>
              </div>

              <!-- Comment 2 -->
              <div class="border-b border-gray-100 pb-6">
                <div class="flex items-start gap-4">
                  <div
                    class="w-10 h-10 rounded-full bg-gray-200 flex-shrink-0 flex items-center justify-center"
                  >
                    <i class="ri-user-line text-gray-600"></i>
                  </div>
                  <div class="flex-1">
                    <div class="flex items-center justify-between mb-2">
                      <div>
                        <span class="font-medium text-gray-800"
                          >Tashi Yangden</span
                        >
                        <span class="text-sm text-gray-500 ml-2"
                          >1 week ago</span
                        >
                      </div>
                      <div class="flex items-center text-gray-500">
                        <div class="w-5 h-5 flex items-center justify-center">
                          <i class="ri-heart-line"></i>
                        </div>
                        <span class="text-sm ml-1">18</span>
                      </div>
                    </div>
                    <p class="text-gray-700">
                      I've been following the mindfulness practices shared in
                      these videos for the past month, and I've noticed a
                      significant improvement in my concentration during study
                      sessions. The techniques are simple yet effective. Looking
                      forward to more content like this!
                    </p>
                  </div>
                </div>
              </div>

              <!-- Comment 3 -->
              <div>
                <div class="flex items-start gap-4">
                  <div
                    class="w-10 h-10 rounded-full bg-gray-200 flex-shrink-0 flex items-center justify-center"
                  >
                    <i class="ri-user-line text-gray-600"></i>
                  </div>
                  <div class="flex-1">
                    <div class="flex items-center justify-between mb-2">
                      <div>
                        <span class="font-medium text-gray-800"
                          >Dorji Tshering</span
                        >
                        <span class="text-sm text-gray-500 ml-2"
                          >2 weeks ago</span
                        >
                      </div>
                      <div class="flex items-center text-gray-500">
                        <div class="w-5 h-5 flex items-center justify-center">
                          <i class="ri-heart-line"></i>
                        </div>
                        <span class="text-sm ml-1">32</span>
                      </div>
                    </div>
                    <p class="text-gray-700">
                      As a teacher in eastern Bhutan, I've been sharing these
                      motivational videos with my students. The content is not
                      only inspiring but also culturally relevant, which makes
                      it easier for students to connect with the messages. Thank
                      you for creating such valuable resources in both Dzongkha
                      and English!
                    </p>
                  </div>
                </div>
              </div>
            </div>

            <!-- Load More Comments -->
            <div class="text-center mt-8">
              <button
                class="px-6 py-2 bg-white text-primary font-medium rounded-button border border-primary hover:bg-gray-50 transition-colors whitespace-nowrap"
              >
                Load More Comments
              </button>
            </div>
          </div>
        </div>
      </section>

      <!-- Student Solutions Section -->
      <section id="solutions" class="py-16 bg-white">
        <div class="container mx-auto px-4">
          <div class="max-w-3xl mx-auto text-center mb-12">
            <h2 class="text-3xl font-bold mb-4">Student Solution Space</h2>
            <p class="text-gray-600">
              Get help with your studies, access past paper solutions, and
              connect with our AI assistant for personalized support.
            </p>
          </div>

          <!-- Solutions Tabs -->
          <div
            class="bg-white rounded-lg shadow-md border border-gray-100 overflow-hidden mb-12"
          >
            <div class="border-b border-gray-100">
              <div class="flex overflow-x-auto">
                <button
                  class="tab-button active px-6 py-4 font-medium text-gray-800 border-b-2 border-transparent focus:outline-none whitespace-nowrap"
                >
                  Past Papers
                </button>
                <button
                  class="tab-button px-6 py-4 font-medium text-gray-800 border-b-2 border-transparent focus:outline-none whitespace-nowrap"
                >
                  Homework Help
                </button>
                <button
                  class="tab-button px-6 py-4 font-medium text-gray-800 border-b-2 border-transparent focus:outline-none whitespace-nowrap"
                >
                  Ask DSpace
                </button>
                <button
                  class="tab-button px-6 py-4 font-medium text-gray-800 border-b-2 border-transparent focus:outline-none whitespace-nowrap"
                >
                  Study Resources
                </button>
              </div>
            </div>

            <!-- Past Papers Content -->
            <div class="p-6">
              <!-- Filter Controls -->
              <div class="flex flex-wrap items-center gap-4 mb-6">
                <div class="w-full md:w-auto">
                  <label class="block text-sm font-medium text-gray-700 mb-1"
                    >Subject</label
                  >
                  <select
                    class="w-full md:w-48 bg-white border border-gray-200 rounded-lg py-2 px-3 pr-8 text-gray-700 focus:outline-none focus:border-primary"
                  >
                    <option>All Subjects</option>
                    <option>Mathematics</option>
                    <option>Science</option>
                    <option>English</option>
                    <option>Dzongkha</option>
                    <option>Social Studies</option>
                    <option>Economics</option>
                  </select>
                </div>
                <div class="w-full md:w-auto">
                  <label class="block text-sm font-medium text-gray-700 mb-1"
                    >Class</label
                  >
                  <select
                    class="w-full md:w-36 bg-white border border-gray-200 rounded-lg py-2 px-3 pr-8 text-gray-700 focus:outline-none focus:border-primary"
                  >
                    <option>All Classes</option>
                    <option>Class 10</option>
                    <option>Class 9</option>
                    <option>Class 8</option>
                    <option>Class 7</option>
                    <option>Class 6</option>
                    <option>Class 5</option>
                    <option>Class 4</option>
                  </select>
                </div>
                <div class="w-full md:w-auto">
                  <label class="block text-sm font-medium text-gray-700 mb-1"
                    >Year</label
                  >
                  <select
                    class="w-full md:w-36 bg-white border border-gray-200 rounded-lg py-2 px-3 pr-8 text-gray-700 focus:outline-none focus:border-primary"
                  >
                    <option>All Years</option>
                    <option>2025</option>
                    <option>2024</option>
                    <option>2023</option>
                    <option>2022</option>
                    <option>2021</option>
                  </select>
                </div>
                <div class="w-full md:w-auto md:ml-auto">
                  <label class="block text-sm font-medium text-gray-700 mb-1"
                    >Search</label
                  >
                  <div class="relative">
                    <input
                      type="text"
                      placeholder="Search papers..."
                      class="w-full md:w-64 py-2 pl-10 pr-4 border border-gray-200 rounded-lg focus:outline-none focus:border-primary"
                    />
                    <div
                      class="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-400"
                    >
                      <i class="ri-search-line"></i>
                    </div>
                  </div>
                </div>
              </div>

              <!-- Past Papers List -->
              <div class="overflow-x-auto">
                <table class="min-w-full">
                  <thead>
                    <tr class="bg-gray-50">
                      <th
                        class="py-3 px-4 text-left text-sm font-medium text-gray-700"
                      >
                        Subject
                      </th>
                      <th
                        class="py-3 px-4 text-left text-sm font-medium text-gray-700"
                      >
                        Class
                      </th>
                      <th
                        class="py-3 px-4 text-left text-sm font-medium text-gray-700"
                      >
                        Year
                      </th>
                      <th
                        class="py-3 px-4 text-left text-sm font-medium text-gray-700"
                      >
                        Type
                      </th>
                      <th
                        class="py-3 px-4 text-left text-sm font-medium text-gray-700"
                      >
                        Actions
                      </th>
                    </tr>
                  </thead>
                  <tbody class="divide-y divide-gray-100">
                    <tr class="hover:bg-gray-50">
                      <td class="py-3 px-4 text-sm text-gray-700">
                        Mathematics
                      </td>
                      <td class="py-3 px-4 text-sm text-gray-700">Class 10</td>
                      <td class="py-3 px-4 text-sm text-gray-700">2024</td>
                      <td class="py-3 px-4 text-sm text-gray-700">
                        Annual Exam
                      </td>
                      <td class="py-3 px-4 text-sm">
                        <div class="flex items-center space-x-3">
                          <a
                            href="#"
                            class="text-primary hover:text-indigo-700 transition-colors"
                          >
                            <div
                              class="w-5 h-5 flex items-center justify-center"
                            >
                              <i class="ri-file-download-line"></i>
                            </div>
                          </a>
                          <a
                            href="#"
                            class="text-primary hover:text-indigo-700 transition-colors"
                          >
                            <div
                              class="w-5 h-5 flex items-center justify-center"
                            >
                              <i class="ri-eye-line"></i>
                            </div>
                          </a>
                        </div>
                      </td>
                    </tr>
                    <tr class="hover:bg-gray-50">
                      <td class="py-3 px-4 text-sm text-gray-700">Science</td>
                      <td class="py-3 px-4 text-sm text-gray-700">Class 10</td>
                      <td class="py-3 px-4 text-sm text-gray-700">2024</td>
                      <td class="py-3 px-4 text-sm text-gray-700">
                        Annual Exam
                      </td>
                      <td class="py-3 px-4 text-sm">
                        <div class="flex items-center space-x-3">
                          <a
                            href="#"
                            class="text-primary hover:text-indigo-700 transition-colors"
                          >
                            <div
                              class="w-5 h-5 flex items-center justify-center"
                            >
                              <i class="ri-file-download-line"></i>
                            </div>
                          </a>
                          <a
                            href="#"
                            class="text-primary hover:text-indigo-700 transition-colors"
                          >
                            <div
                              class="w-5 h-5 flex items-center justify-center"
                            >
                              <i class="ri-eye-line"></i>
                            </div>
                          </a>
                        </div>
                      </td>
                    </tr>
                    <tr class="hover:bg-gray-50">
                      <td class="py-3 px-4 text-sm text-gray-700">English</td>
                      <td class="py-3 px-4 text-sm text-gray-700">Class 10</td>
                      <td class="py-3 px-4 text-sm text-gray-700">2024</td>
                      <td class="py-3 px-4 text-sm text-gray-700">
                        Annual Exam
                      </td>
                      <td class="py-3 px-4 text-sm">
                        <div class="flex items-center space-x-3">
                          <a
                            href="#"
                            class="text-primary hover:text-indigo-700 transition-colors"
                          >
                            <div
                              class="w-5 h-5 flex items-center justify-center"
                            >
                              <i class="ri-file-download-line"></i>
                            </div>
                          </a>
                          <a
                            href="#"
                            class="text-primary hover:text-indigo-700 transition-colors"
                          >
                            <div
                              class="w-5 h-5 flex items-center justify-center"
                            >
                              <i class="ri-eye-line"></i>
                            </div>
                          </a>
                        </div>
                      </td>
                    </tr>
                    <tr class="hover:bg-gray-50">
                      <td class="py-3 px-4 text-sm text-gray-700">
                        Mathematics
                      </td>
                      <td class="py-3 px-4 text-sm text-gray-700">Class 9</td>
                      <td class="py-3 px-4 text-sm text-gray-700">2024</td>
                      <td class="py-3 px-4 text-sm text-gray-700">Mid-Term</td>
                      <td class="py-3 px-4 text-sm">
                        <div class="flex items-center space-x-3">
                          <a
                            href="#"
                            class="text-primary hover:text-indigo-700 transition-colors"
                          >
                            <div
                              class="w-5 h-5 flex items-center justify-center"
                            >
                              <i class="ri-file-download-line"></i>
                            </div>
                          </a>
                          <a
                            href="#"
                            class="text-primary hover:text-indigo-700 transition-colors"
                          >
                            <div
                              class="w-5 h-5 flex items-center justify-center"
                            >
                              <i class="ri-eye-line"></i>
                            </div>
                          </a>
                        </div>
                      </td>
                    </tr>
                    <tr class="hover:bg-gray-50">
                      <td class="py-3 px-4 text-sm text-gray-700">
                        Social Studies
                      </td>
                      <td class="py-3 px-4 text-sm text-gray-700">Class 8</td>
                      <td class="py-3 px-4 text-sm text-gray-700">2023</td>
                      <td class="py-3 px-4 text-sm text-gray-700">
                        Annual Exam
                      </td>
                      <td class="py-3 px-4 text-sm">
                        <div class="flex items-center space-x-3">
                          <a
                            href="#"
                            class="text-primary hover:text-indigo-700 transition-colors"
                          >
                            <div
                              class="w-5 h-5 flex items-center justify-center"
                            >
                              <i class="ri-file-download-line"></i>
                            </div>
                          </a>
                          <a
                            href="#"
                            class="text-primary hover:text-indigo-700 transition-colors"
                          >
                            <div
                              class="w-5 h-5 flex items-center justify-center"
                            >
                              <i class="ri-eye-line"></i>
                            </div>
                          </a>
                        </div>
                      </td>
                    </tr>
                  </tbody>
                </table>
              </div>

              <!-- Pagination -->
              <div class="flex items-center justify-between mt-6">
                <div class="text-sm text-gray-600">
                  Showing <span class="font-medium">1</span> to
                  <span class="font-medium">5</span> of
                  <span class="font-medium">42</span> results
                </div>
                <div class="flex items-center space-x-2">
                  <button
                    class="w-9 h-9 flex items-center justify-center rounded-lg border border-gray-200 text-gray-500 hover:border-primary hover:text-primary transition-colors"
                  >
                    <i class="ri-arrow-left-s-line"></i>
                  </button>
                  <button
                    class="w-9 h-9 flex items-center justify-center rounded-lg bg-primary text-white"
                  >
                    1
                  </button>
                  <button
                    class="w-9 h-9 flex items-center justify-center rounded-lg border border-gray-200 text-gray-700 hover:border-primary hover:text-primary transition-colors"
                  >
                    2
                  </button>
                  <button
                    class="w-9 h-9 flex items-center justify-center rounded-lg border border-gray-200 text-gray-700 hover:border-primary hover:text-primary transition-colors"
                  >
                    3
                  </button>
                  <button
                    class="w-9 h-9 flex items-center justify-center rounded-lg border border-gray-200 text-gray-500 hover:border-primary hover:text-primary transition-colors"
                  >
                    <i class="ri-arrow-right-s-line"></i>
                  </button>
                </div>
              </div>
            </div>
          </div>

          <!-- AI Assistant Promo -->
          <div
            class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center bg-indigo-50 rounded-lg p-8"
          >
            <div>
              <h3 class="text-2xl font-semibold mb-4">
                Meet Alu - Your AI Study Assistant
              </h3>
              <p class="text-gray-600 mb-6">
                Alu is your friendly AI assistant that can help with homework
                questions, explain difficult concepts, and provide personalized
                learning support in both English and Dzongkha.
              </p>
              <ul class="space-y-3 mb-6">
                <li class="flex items-start">
                  <div
                    class="w-5 h-5 flex items-center justify-center text-primary mt-0.5 mr-2"
                  >
                    <i class="ri-check-line"></i>
                  </div>
                  <span class="text-gray-700"
                    >Get instant answers to your academic questions</span
                  >
                </li>
                <li class="flex items-start">
                  <div
                    class="w-5 h-5 flex items-center justify-center text-primary mt-0.5 mr-2"
                  >
                    <i class="ri-check-line"></i>
                  </div>
                  <span class="text-gray-700"
                    >Step-by-step explanations for math and science
                    problems</span
                  >
                </li>
                <li class="flex items-start">
                  <div
                    class="w-5 h-5 flex items-center justify-center text-primary mt-0.5 mr-2"
                  >
                    <i class="ri-check-line"></i>
                  </div>
                  <span class="text-gray-700"
                    >Available 24/7 for homework help and study guidance</span
                  >
                </li>
                <li class="flex items-start">
                  <div
                    class="w-5 h-5 flex items-center justify-center text-primary mt-0.5 mr-2"
                  >
                    <i class="ri-check-line"></i>
                  </div>
                  <span class="text-gray-700"
                    >Support in both English and Dzongkha languages</span
                  >
                </li>
              </ul>
              <button
                class="px-6 py-3 bg-primary text-white font-medium rounded-button hover:bg-indigo-600 transition-colors shadow-md hover:shadow-lg whitespace-nowrap"
              >
                Chat with Alu Now
              </button>
            </div>
            <div class="flex justify-center">
              <img
                src="https://readdy.ai/api/search-image?query=friendly%2520AI%2520assistant%2520robot%2520character%2520with%2520Bhutanese%2520design%2520elements%252C%2520educational%2520context%252C%2520digital%2520illustration%252C%2520clean%2520background%252C%2520professional%2520character%2520design&width=500&height=500&seq=alu1&orientation=squarish"
                alt="Alu AI Assistant"
                class="max-w-full h-auto rounded-lg shadow-lg"
              />
            </div>
          </div>
        </div>
      </section>

      <!-- About Section -->
      <section id="about" class="py-16 bg-gray-50">
        <div class="container mx-auto px-4">
          <div class="max-w-3xl mx-auto text-center mb-12">
            <h2 class="text-3xl font-bold mb-4">About DSpace Bhutan</h2>
            <p class="text-gray-600">
              Learn about our mission to empower Bhutanese youth through digital
              education and technology skills.
            </p>
          </div>

          <div
            class="grid grid-cols-1 md:grid-cols-2 gap-12 items-center mb-16"
          >
            <div>
              <h3 class="text-2xl font-semibold mb-4">Our Story</h3>
              <p class="text-gray-700 mb-4">
                DSpace Bhutan was founded by Kinley Penjor in 2023 with a vision
                to bridge the digital divide in Bhutan's education system. As a
                technology enthusiast and educator, Kinley recognized the need
                for accessible, high-quality digital learning resources in both
                Dzongkha and English.
              </p>
              <p class="text-gray-700 mb-4">
                What started as a small YouTube channel sharing tech tips has
                grown into a comprehensive digital platform serving thousands of
                Bhutanese students and learners across the country, from urban
                centers to remote villages.
              </p>
              <p class="text-gray-700">
                Today, DSpace Bhutan continues to expand its offerings, working
                closely with educators, technology experts, and students to
                create relevant, engaging content that empowers the next
                generation of Bhutanese innovators and leaders.
              </p>
            </div>
            <div class="flex justify-center">
              <img
                src="https://readdy.ai/api/search-image?query=Bhutanese%2520classroom%2520with%2520students%2520using%2520computers%2520or%2520digital%2520devices%252C%2520modern%2520educational%2520setting%2520with%2520traditional%2520Bhutanese%2520elements%252C%2520bright%2520natural%2520lighting%252C%2520professional%2520photography%252C%2520clean%2520composition&width=600&height=400&seq=class1&orientation=landscape"
                alt="Bhutanese Classroom"
                class="rounded-lg shadow-lg max-w-full h-auto"
              />
            </div>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-3 gap-8 mb-16">
            <div
              class="bg-white rounded-lg shadow-sm p-6 border border-gray-100"
            >
              <div
                class="w-12 h-12 flex items-center justify-center rounded-full bg-indigo-100 text-primary mb-4"
              >
                <i class="ri-eye-line text-xl"></i>
              </div>
              <h3 class="text-xl font-semibold mb-2">Our Vision</h3>
              <p class="text-gray-600">
                To create a digitally empowered Bhutan where every student has
                access to quality educational resources regardless of their
                location or background.
              </p>
            </div>
            <div
              class="bg-white rounded-lg shadow-sm p-6 border border-gray-100"
            >
              <div
                class="w-12 h-12 flex items-center justify-center rounded-full bg-indigo-100 text-primary mb-4"
              >
                <i class="ri-flag-line text-xl"></i>
              </div>
              <h3 class="text-xl font-semibold mb-2">Our Mission</h3>
              <p class="text-gray-600">
                To provide accessible, high-quality digital education content
                that bridges the gap between traditional learning and modern
                technology skills.
              </p>
            </div>
            <div
              class="bg-white rounded-lg shadow-sm p-6 border border-gray-100"
            >
              <div
                class="w-12 h-12 flex items-center justify-center rounded-full bg-indigo-100 text-primary mb-4"
              >
                <i class="ri-heart-line text-xl"></i>
              </div>
              <h3 class="text-xl font-semibold mb-2">Our Values</h3>
              <p class="text-gray-600">
                We believe in accessibility, cultural relevance, innovation, and
                community engagement as the core principles guiding our work.
              </p>
            </div>
          </div>

          <!-- Founder Profile -->
          <div
            class="bg-white rounded-lg shadow-md overflow-hidden border border-gray-100"
          >
            <div class="grid grid-cols-1 md:grid-cols-3">
              <div
                class="md:col-span-1 bg-indigo-50 p-8 flex items-center justify-center"
              >
                <img
                  src="https://readdy.ai/api/search-image?query=professional%2520portrait%2520of%2520Bhutanese%2520man%2520in%2520business%2520casual%2520attire%252C%2520friendly%2520expression%252C%2520clean%2520background%252C%2520professional%2520headshot%2520photography%252C%2520educational%2520context&width=400&height=500&seq=founder1&orientation=portrait"
                  alt="Kinley Penjor"
                  class="rounded-full w-48 h-48 object-cover border-4 border-white shadow-md"
                />
              </div>
              <div class="md:col-span-2 p-8">
                <h3 class="text-2xl font-semibold mb-2">Kinley Penjor</h3>
                <p class="text-gray-600 mb-4">Founder & CEO, DSpace Bhutan</p>
                <p class="text-gray-700 mb-4">
                  Kinley Penjor is an educator, technologist, and digital
                  content creator passionate about bridging the digital divide
                  in Bhutan's education system. With a background in Computer
                  Science and Education, Kinley has worked with various
                  educational institutions to integrate technology into
                  traditional learning environments.
                </p>
                <p class="text-gray-700 mb-6">
                  After witnessing the challenges faced by students in accessing
                  quality educational resources, especially in remote areas,
                  Kinley founded DSpace Bhutan to create a platform that
                  provides curriculum-aligned content, tech skills, and
                  inspiration to Bhutanese youth in both national languages.
                </p>
                <div class="flex space-x-4">
                  <a
                    href="#"
                    class="w-10 h-10 flex items-center justify-center rounded-full bg-gray-100 text-gray-700 hover:bg-primary hover:text-white transition-colors"
                  >
                    <i class="ri-youtube-line"></i>
                  </a>
                  <a
                    href="#"
                    class="w-10 h-10 flex items-center justify-center rounded-full bg-gray-100 text-gray-700 hover:bg-primary hover:text-white transition-colors"
                  >
                    <i class="ri-facebook-line"></i>
                  </a>
                  <a
                    href="#"
                    class="w-10 h-10 flex items-center justify-center rounded-full bg-gray-100 text-gray-700 hover:bg-primary hover:text-white transition-colors"
                  >
                    <i class="ri-instagram-line"></i>
                  </a>
                  <a
                    href="#"
                    class="w-10 h-10 flex items-center justify-center rounded-full bg-gray-100 text-gray-700 hover:bg-primary hover:text-white transition-colors"
                  >
                    <i class="ri-linkedin-line"></i>
                  </a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Contact Section -->
      <section class="py-16 bg-white">
        <div class="container mx-auto px-4">
          <div class="max-w-3xl mx-auto text-center mb-12">
            <h2 class="text-3xl font-bold mb-4">Get in Touch</h2>
            <p class="text-gray-600">
              Have questions or suggestions? Reach out to us through any of
              these channels.
            </p>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-start">
            <!-- Contact Form -->
            <div
              class="bg-white rounded-lg shadow-md p-8 border border-gray-100"
            >
              <h3 class="text-xl font-semibold mb-6">Send Us a Message</h3>
              <form>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
                  <div>
                    <label class="block text-sm font-medium text-gray-700 mb-1"
                      >Your Name</label
                    >
                    <input
                      type="text"
                      class="w-full p-3 border border-gray-200 rounded-lg focus:outline-none focus:border-primary transition-colors"
                    />
                  </div>
                  <div>
                    <label class="block text-sm font-medium text-gray-700 mb-1"
                      >Email Address</label
                    >
                    <input
                      type="email"
                      class="w-full p-3 border border-gray-200 rounded-lg focus:outline-none focus:border-primary transition-colors"
                    />
                  </div>
                </div>
                <div class="mb-6">
                  <label class="block text-sm font-medium text-gray-700 mb-1"
                    >Subject</label
                  >
                  <input
                    type="text"
                    class="w-full p-3 border border-gray-200 rounded-lg focus:outline-none focus:border-primary transition-colors"
                  />
                </div>
                <div class="mb-6">
                  <label class="block text-sm font-medium text-gray-700 mb-1"
                    >Your Message</label
                  >
                  <textarea
                    rows="5"
                    class="w-full p-3 border border-gray-200 rounded-lg focus:outline-none focus:border-primary transition-colors resize-none"
                  ></textarea>
                </div>
                <button
                  type="submit"
                  class="w-full py-3 bg-primary text-white font-medium rounded-button hover:bg-indigo-600 transition-colors shadow-md hover:shadow-lg whitespace-nowrap"
                >
                  Send Message
                </button>
              </form>
            </div>

            <!-- Contact Info -->
            <div>
              <div
                class="bg-white rounded-lg shadow-md p-8 border border-gray-100 mb-8"
              >
                <h3 class="text-xl font-semibold mb-6">Contact Information</h3>
                <ul class="space-y-4">
                  <li class="flex items-start">
                    <div
                      class="w-10 h-10 flex items-center justify-center rounded-full bg-indigo-100 text-primary mr-4"
                    >
                      <i class="ri-mail-line"></i>
                    </div>
                    <div>
                      <span class="block text-sm font-medium text-gray-700"
                        >Email</span
                      >
                      <a
                        href="mailto:info@dspacebhutan.bt"
                        class="text-gray-600 hover:text-primary transition-colors"
                        >info@dspacebhutan.bt</a
                      >
                    </div>
                  </li>
                  <li class="flex items-start">
                    <div
                      class="w-10 h-10 flex items-center justify-center rounded-full bg-indigo-100 text-primary mr-4"
                    >
                      <i class="ri-phone-line"></i>
                    </div>
                    <div>
                      <span class="block text-sm font-medium text-gray-700"
                        >Phone</span
                      >
                      <a
                        href="tel:+97517123456"
                        class="text-gray-600 hover:text-primary transition-colors"
                        >+975 17 123 456</a
                      >
                    </div>
                  </li>
                  <li class="flex items-start">
                    <div
                      class="w-10 h-10 flex items-center justify-center rounded-full bg-indigo-100 text-primary mr-4"
                    >
                      <i class="ri-map-pin-line"></i>
                    </div>
                    <div>
                      <span class="block text-sm font-medium text-gray-700"
                        >Location</span
                      >
                      <span class="text-gray-600">Thimphu, Bhutan</span>
                    </div>
                  </li>
                </ul>
              </div>

              <div
                class="bg-white rounded-lg shadow-md p-8 border border-gray-100"
              >
                <h3 class="text-xl font-semibold mb-6">Connect With Us</h3>
                <div class="grid grid-cols-2 gap-4">
                  <a
                    href="#"
                    class="flex items-center p-4 rounded-lg border border-gray-200 hover:border-primary hover:bg-indigo-50 transition-colors"
                  >
                    <div
                      class="w-10 h-10 flex items-center justify-center rounded-full bg-red-100 text-red-600 mr-3"
                    >
                      <i class="ri-youtube-fill"></i>
                    </div>
                    <span class="font-medium text-gray-700">YouTube</span>
                  </a>
                  <a
                    href="#"
                    class="flex items-center p-4 rounded-lg border border-gray-200 hover:border-primary hover:bg-indigo-50 transition-colors"
                  >
                    <div
                      class="w-10 h-10 flex items-center justify-center rounded-full bg-blue-100 text-blue-600 mr-3"
                    >
                      <i class="ri-facebook-fill"></i>
                    </div>
                    <span class="font-medium text-gray-700">Facebook</span>
                  </a>
                  <a
                    href="#"
                    class="flex items-center p-4 rounded-lg border border-gray-200 hover:border-primary hover:bg-indigo-50 transition-colors"
                  >
                    <div
                      class="w-10 h-10 flex items-center justify-center rounded-full bg-pink-100 text-pink-600 mr-3"
                    >
                      <i class="ri-instagram-fill"></i>
                    </div>
                    <span class="font-medium text-gray-700">Instagram</span>
                  </a>
                  <a
                    href="#"
                    class="flex items-center p-4 rounded-lg border border-gray-200 hover:border-primary hover:bg-indigo-50 transition-colors"
                  >
                    <div
                      class="w-10 h-10 flex items-center justify-center rounded-full bg-cyan-100 text-cyan-600 mr-3"
                    >
                      <i class="ri-twitter-x-fill"></i>
                    </div>
                    <span class="font-medium text-gray-700">Twitter</span>
                  </a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Newsletter Section -->
      <section class="py-16 bg-indigo-50">
        <div class="container mx-auto px-4">
          <div class="max-w-3xl mx-auto text-center">
            <h2 class="text-3xl font-bold mb-4">Stay Updated</h2>
            <p class="text-gray-600 mb-8">
              Subscribe to our newsletter to receive the latest updates, new
              content alerts, and educational resources.
            </p>
            <div class="flex flex-col sm:flex-row gap-4 max-w-md mx-auto">
              <input
                type="email"
                placeholder="Your email address"
                class="flex-1 p-3 rounded-lg border-none focus:outline-none focus:ring-2 focus:ring-primary shadow-sm"
              />
              <button
                class="px-6 py-3 bg-primary text-white font-medium rounded-button hover:bg-indigo-600 transition-colors shadow-md hover:shadow-lg whitespace-nowrap"
              >
                Subscribe
              </button>
            </div>
          </div>
        </div>
      </section>
    </main>

    <!-- Footer -->
    <footer class="bg-gray-900 text-white pt-16 pb-8">
      <div class="container mx-auto px-4">
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 mb-12">
          <div>
            <div class="flex items-center space-x-2 mb-6">
              <span class="text-2xl font-['Pacifico'] text-white">DSpace</span>
              <span class="text-lg font-semibold">Bhutan</span>
            </div>
            <p class="text-gray-400 mb-6">
              Empowering Bhutanese youth through digital education, technology
              skills, and inspiration.
            </p>
            <div class="flex space-x-4">
              <a
                href="#"
                class="w-9 h-9 flex items-center justify-center rounded-full bg-gray-800 text-gray-400 hover:bg-primary hover:text-white transition-colors"
              >
                <i class="ri-youtube-line"></i>
              </a>
              <a
                href="#"
                class="w-9 h-9 flex items-center justify-center rounded-full bg-gray-800 text-gray-400 hover:bg-primary hover:text-white transition-colors"
              >
                <i class="ri-facebook-line"></i>
              </a>
              <a
                href="#"
                class="w-9 h-9 flex items-center justify-center rounded-full bg-gray-800 text-gray-400 hover:bg-primary hover:text-white transition-colors"
              >
                <i class="ri-instagram-line"></i>
              </a>
              <a
                href="#"
                class="w-9 h-9 flex items-center justify-center rounded-full bg-gray-800 text-gray-400 hover:bg-primary hover:text-white transition-colors"
              >
                <i class="ri-twitter-x-line"></i>
              </a>
            </div>
          </div>

          <div>
            <h3 class="text-lg font-semibold mb-6">Quick Links</h3>
            <ul class="space-y-3">
              <li>
                <a
                  href="#home"
                  class="text-gray-400 hover:text-white transition-colors"
                  >Home</a
                >
              </li>
              <li>
                <a
                  href="#knowledge-hub"
                  class="text-gray-400 hover:text-white transition-colors"
                  >Knowledge Hub</a
                >
              </li>
              <li>
                <a
                  href="#tech-tips"
                  class="text-gray-400 hover:text-white transition-colors"
                  >Tech Tips</a
                >
              </li>
              <li>
                <a
                  href="#motivation"
                  class="text-gray-400 hover:text-white transition-colors"
                  >Dream Series</a
                >
              </li>
              <li>
                <a
                  href="#solutions"
                  class="text-gray-400 hover:text-white transition-colors"
                  >Student Solutions</a
                >
              </li>
              <li>
                <a
                  href="#about"
                  class="text-gray-400 hover:text-white transition-colors"
                  >About Us</a
                >
              </li>
            </ul>
          </div>

          <div>
            <h3 class="text-lg font-semibold mb-6">Resources</h3>
            <ul class="space-y-3">
              <li>
                <a
                  href="#"
                  class="text-gray-400 hover:text-white transition-colors"
                  >Past Papers</a
                >
              </li>
              <li>
                <a
                  href="#"
                  class="text-gray-400 hover:text-white transition-colors"
                  >Study Materials</a
                >
              </li>
              <li>
                <a
                  href="#"
                  class="text-gray-400 hover:text-white transition-colors"
                  >Video Tutorials</a
                >
              </li>
              <li>
                <a
                  href="#"
                  class="text-gray-400 hover:text-white transition-colors"
                  >AI Assistant</a
                >
              </li>
              <li>
                <a
                  href="#"
                  class="text-gray-400 hover:text-white transition-colors"
                  >FAQ</a
                >
              </li>
              <li>
                <a
                  href="#"
                  class="text-gray-400 hover:text-white transition-colors"
                  >Help Center</a
                >
              </li>
            </ul>
          </div>

          <div>
            <h3 class="text-lg font-semibold mb-6">Contact</h3>
            <ul class="space-y-3">
              <li class="flex items-start">
                <div
                  class="w-5 h-5 flex items-center justify-center text-gray-400 mt-0.5 mr-3"
                >
                  <i class="ri-mail-line"></i>
                </div>
                <span class="text-gray-400">info@dspacebhutan.bt</span>
              </li>
              <li class="flex items-start">
                <div
                  class="w-5 h-5 flex items-center justify-center text-gray-400 mt-0.5 mr-3"
                >
                  <i class="ri-phone-line"></i>
                </div>
                <span class="text-gray-400">+975 17 123 456</span>
              </li>
              <li class="flex items-start">
                <div
                  class="w-5 h-5 flex items-center justify-center text-gray-400 mt-0.5 mr-3"
                >
                  <i class="ri-map-pin-line"></i>
                </div>
                <span class="text-gray-400">Thimphu, Bhutan</span>
              </li>
            </ul>
          </div>
        </div>

        <div
          class="pt-8 border-t border-gray-800 flex flex-col md:flex-row justify-between items-center"
        >
          <p class="text-gray-500 mb-4 md:mb-0">
            © 2025 DSpace Bhutan. All rights reserved.
          </p>
          <div class="flex space-x-6">
            <a href="#" class="text-gray-500 hover:text-white transition-colors"
              >Privacy Policy</a
            >
            <a href="#" class="text-gray-500 hover:text-white transition-colors"
              >Terms of Service</a
            >
            <a href="#" class="text-gray-500 hover:text-white transition-colors"
              >Cookie Policy</a
            >
          </div>
        </div>
      </div>
    </footer>

    <!-- AI Chatbot Button -->
    <div id="chatbot-button" class="fixed bottom-6 right-6 z-50">
      <button
        class="w-16 h-16 bg-primary rounded-full shadow-lg flex items-center justify-center text-white hover:bg-indigo-600 transition-colors"
      >
        <i class="ri-robot-line text-2xl"></i>
      </button>
    </div>

    <!-- AI Chatbot Container -->
    <div
      id="chatbot-container"
      class="chatbot-container fixed bottom-24 right-6 w-80 md:w-96 bg-white rounded-lg shadow-xl z-50 overflow-hidden transform scale-0 origin-bottom-right"
    >
      <div class="bg-primary text-white p-4 flex items-center justify-between">
        <div class="flex items-center">
          <div
            class="w-10 h-10 rounded-full bg-white bg-opacity-20 flex items-center justify-center mr-3"
          >
            <i class="ri-robot-line text-xl"></i>
          </div>
          <div>
            <h3 class="font-medium">Alu</h3>
            <p class="text-xs text-indigo-100">Your AI Study Assistant</p>
          </div>
        </div>
        <button
          id="close-chatbot"
          class="w-8 h-8 flex items-center justify-center rounded-full hover:bg-white hover:bg-opacity-20 transition-colors"
        >
          <i class="ri-close-line text-xl"></i>
        </button>
      </div>
      <div class="h-80 overflow-y-auto p-4 bg-gray-50">
        <!-- Chat messages will appear here -->
        <div class="flex items-start mb-4">
          <div
            class="w-8 h-8 rounded-full bg-indigo-100 flex items-center justify-center flex-shrink-0 mr-2"
          >
            <i class="ri-robot-line text-primary text-sm"></i>
          </div>
          <div class="bg-white p-3 rounded-lg shadow-sm max-w-[80%]">
            <p class="text-gray-700">
              Hello! I'm Alu, your AI study assistant. How can I help you today?
            </p>
          </div>
        </div>
      </div>
      <div class="p-4 border-t border-gray-200">
        <div class="flex gap-2">
          <input
            type="text"
            placeholder="Type your question..."
            class="flex-1 p-2 border border-gray-200 rounded-lg focus:outline-none focus:border-primary"
          />
          <button
            class="w-10 h-10 flex items-center justify-center rounded-full bg-primary text-white"
          >
            <i class="ri-send-plane-fill"></i>
          </button>
        </div>
        <div class="flex flex-wrap gap-2 mt-3">
          <button
            class="px-3 py-1 text-xs bg-gray-100 text-gray-700 rounded-full hover:bg-gray-200 transition-colors whitespace-nowrap"
          >
            How to solve equations?
          </button>
          <button
            class="px-3 py-1 text-xs bg-gray-100 text-gray-700 rounded-full hover:bg-gray-200 transition-colors whitespace-nowrap"
          >
            Windows shortcuts
          </button>
          <button
            class="px-3 py-1 text-xs bg-gray-100 text-gray-700 rounded-full hover:bg-gray-200 transition-colors whitespace-nowrap"
          >
            Study tips
          </button>
        </div>
      </div>
    </div>

    <!-- Scripts -->
    <script id="navigation-script">
      document.addEventListener("DOMContentLoaded", function () {
        // Mobile menu toggle
        const mobileMenuToggle = document.getElementById("mobile-menu-toggle");
        const mobileMenu = document.getElementById("mobile-menu");

        if (mobileMenuToggle && mobileMenu) {
          mobileMenuToggle.addEventListener("click", function () {
            mobileMenu.classList.toggle("hidden");
          });
        }

        // Language dropdown toggle
        const languageToggle = document.getElementById("language-toggle");
        const languageDropdown = document.getElementById("language-dropdown");

        if (languageToggle && languageDropdown) {
          languageToggle.addEventListener("click", function () {
            languageDropdown.classList.toggle("open");
          });

          // Close dropdown when clicking outside
          document.addEventListener("click", function (event) {
            if (
              !languageToggle.contains(event.target) &&
              !languageDropdown.contains(event.target)
            ) {
              languageDropdown.classList.remove("open");
            }
          });
        }

        // Active link highlighting
        const navLinks = document.querySelectorAll(".nav-link");
        const sections = document.querySelectorAll("section[id]");

        function highlightNavLink() {
          const scrollPosition = window.scrollY;

          sections.forEach((section) => {
            const sectionTop = section.offsetTop - 100;
            const sectionHeight = section.offsetHeight;
            const sectionId = section.getAttribute("id");

            if (
              scrollPosition >= sectionTop &&
              scrollPosition < sectionTop + sectionHeight
            ) {
              navLinks.forEach((link) => {
                link.classList.remove("active");
                if (link.getAttribute("href") === `#${sectionId}`) {
                  link.classList.add("active");
                }
              });
            }
          });
        }

        window.addEventListener("scroll", highlightNavLink);
        highlightNavLink();
      });
    </script>

    <script id="tabs-script">
      document.addEventListener("DOMContentLoaded", function () {
        // Tab switching functionality
        const tabButtons = document.querySelectorAll(".tab-button");

        if (tabButtons.length > 0) {
          tabButtons.forEach((button) => {
            button.addEventListener("click", function () {
              // Remove active class from all buttons
              tabButtons.forEach((btn) => {
                btn.classList.remove("active");
              });

              // Add active class to clicked button
              this.classList.add("active");

              // Here you would normally show/hide tab content
              // For this demo, we're just showing the active state on the button
            });
          });
        }
      });
    </script>

    <script id="chatbot-script">
      document.addEventListener("DOMContentLoaded", function () {
        const chatbotButton = document.getElementById("chatbot-button");
        const chatbotContainer = document.getElementById("chatbot-container");
        const closeChatbot = document.getElementById("close-chatbot");

        if (chatbotButton && chatbotContainer && closeChatbot) {
          chatbotButton.addEventListener("click", function () {
            chatbotContainer.style.transform = "scale(1)";
          });

          closeChatbot.addEventListener("click", function () {
            chatbotContainer.style.transform = "scale(0)";
          });
        }
      });
    </script>

    <script id="theme-toggle-script">
      document.addEventListener("DOMContentLoaded", function () {
        const themeToggles = document.querySelectorAll(".theme-toggle");

        if (themeToggles.length > 0) {
          themeToggles.forEach((toggle) => {
            toggle.addEventListener("change", function () {
              // Here you would implement dark/light mode switching
              // For this demo, we're just showing the toggle state
              document.querySelectorAll(".theme-toggle").forEach((t) => {
                t.checked = this.checked;
              });
            });
          });
        }
      });
    </script>
  </body>
</html>
