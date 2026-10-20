


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.5, user-scalable=yes">
  <title>MediCareers | Trusted Healthcare Jobs</title>
  <!-- Tailwind CSS via CDN (lightweight, production-ready utility framework) -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Custom CSS block (best practices, minimal) -->
  <style>
    /* ===== GLOBAL & LAYOUT ===== */
    body {
      background-color: #f8fafc; /* soft gray background */
      font-family: system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', sans-serif;
    }
    /* Smooth focus rings for accessibility */
    :focus-visible {
      outline: 3px solid #2563eb;
      outline-offset: 2px;
    }
    /* Modal backdrop animation */
    .modal-backdrop {
      background-color: rgba(15, 23, 42, 0.6);
      backdrop-filter: blur(4px);
      transition: opacity 0.2s ease;
    }
    /* Card hover micro-interaction */
    .job-card {
      transition: transform 0.2s ease, box-shadow 0.2s ease, border-color 0.2s ease;
    }
    .job-card:hover {
      transform: translateY(-2px);
      box-shadow: 0 12px 24px -8px rgba(0, 0, 0, 0.08), 0 4px 8px -4px rgba(0, 0, 0, 0.02);
      border-color: #93c5fd; /* light medical blue */
    }
    /* Payment success pulse */
    @keyframes softPulse {
      0% { opacity: 0.8; transform: scale(0.98); }
      100% { opacity: 1; transform: scale(1); }
    }
    .payment-success {
      animation: softPulse 0.4s ease-out;
    }
    /* Disabled button style */
    .btn-disabled {
      opacity: 0.5;
      pointer-events: none;
      cursor: not-allowed;
    }
    /* Custom scroll for modal (if needed) */
    .modal-content {
      max-height: 90vh;
      overflow-y: auto;
      scrollbar-width: thin;
      scrollbar-color: #cbd5e1 #f1f5f9;
    }
    .modal-content::-webkit-scrollbar {
      width: 6px;
    }
    .modal-content::-webkit-scrollbar-track {
      background: #f1f5f9;
      border-radius: 8px;
    }
    .modal-content::-webkit-scrollbar-thumb {
      background: #cbd5e1;
      border-radius: 8px;
    }
  </style>
</head>
<body class="antialiased text-slate-800">

  <!-- ========== HEADER / NAVIGATION ========== -->
  <header class="bg-white border-b border-slate-200 sticky top-0 z-10 shadow-sm">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex items-center justify-between h-16">
      <!-- Logo / Brand -->
      <a href="#" class="flex items-center gap-2 focus:outline-none focus-visible:ring-2 focus-visible:ring-blue-500 rounded" aria-label="MediCareers home">
        <span class="text-blue-700 text-2xl font-bold tracking-tight">Medi</span><span class="text-slate-600 text-2xl font-medium">Careers</span>
        <span class="hidden sm:inline-block ml-2 text-xs bg-blue-50 text-blue-700 px-2 py-0.5 rounded-full border border-blue-100">trusted hiring</span>
      </a>
      <!-- Desktop nav (minimal) -->
      <nav class="hidden md:flex items-center gap-6 text-sm font-medium text-slate-600">
        <a href="#" class="hover:text-blue-700 transition-colors duration-150">Find Jobs</a>
        <a href="#" class="hover:text-blue-700 transition-colors duration-150">For Employers</a>
        <a href="#" class="hover:text-blue-700 transition-colors duration-150">Resources</a>
      </nav>
      <!-- Sign in (mock) -->
      <button class="text-sm font-medium text-slate-700 border border-slate-300 rounded-full px-4 py-1.5 hover:bg-slate-50 hover:border-slate-400 transition-colors duration-150 focus-visible:ring-2">
        Sign in
      </button>
    </div>
  </header>

  <main>
    <!-- ========== HERO + SEARCH ========== -->
    <section class="bg-gradient-to-b from-white to-blue-50/30 py-10 sm:py-14 md:py-16 border-b border-slate-200/60">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center max-w-3xl mx-auto">
          <h1 class="text-3xl sm:text-4xl md:text-5xl font-bold tracking-tight text-slate-900 leading-tight">
            Find your next <span class="text-blue-700">healthcare</span> role
          </h1>
          <p class="mt-4 text-base sm:text-lg text-slate-600">
            Trusted by hospitals and clinicians. Search thousands of verified openings.
          </p>
        </div>

        <!-- Search bar with active state (focus ring via Tailwind) -->
        <div class="mt-8 max-w-2xl mx-auto">
          <form class="flex flex-col sm:flex-row gap-3 bg-white p-2 rounded-2xl shadow-md border border-slate-200/80 focus-within:ring-4 focus-within:ring-blue-200/70 transition-all duration-150" onsubmit="event.preventDefault(); alert('Search demo: use the job feed below.');">
            <div class="flex-1 flex items-center gap-2 px-3 py-2 bg-slate-50/80 rounded-xl border border-transparent focus-within:border-blue-300 focus-within:bg-white transition-all">
              <svg class="w-5 h-5 text-slate-400 shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"/></svg>
              <input type="search" placeholder="Job title, specialty, or hospital" class="w-full bg-transparent border-none outline-none text-slate-800 placeholder-slate-400 text-sm sm:text-base" aria-label="Search jobs by title, specialty, or hospital">
            </div>
            <button type="submit" class="bg-blue-700 hover:bg-blue-800 text-white font-medium px-6 py-3 sm:py-2.5 rounded-xl shadow-sm transition-all duration-150 focus-visible:ring-2 focus-visible:ring-blue-500 focus-visible:ring-offset-1 flex items-center justify-center gap-2">
              <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"/></svg>
              <span>Search</span>
            </button>
          </form>
          <p class="mt-3 text-xs text-slate-500 text-center sm:text-left">Popular: ICU Nurse, Surgical Tech, Hospital Admin, Radiologist</p>
        </div>
      </div>
    </section>

    <!-- ========== FEATURED JOB FEED ========== -->
    <section class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-10 md:py-14">
      <div class="flex items-center justify-between mb-6">
        <h2 class="text-2xl font-semibold tracking-tight text-slate-900">Featured openings</h2>
        <span class="text-sm text-slate-500 bg-slate-100 px-3 py-1 rounded-full">6 positions</span>
      </div>

      <!-- Job Grid: responsive using CSS Grid via Tailwind -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-5">
        
        <!-- Job Card 1: Nursing -->
        <article class="job-card bg-white rounded-2xl border border-slate-200 p-5 shadow-sm flex flex-col">
          <div class="flex items-start justify-between">
            <div>
              <h3 class="text-lg font-semibold text-slate-900 leading-snug">Registered Nurse – ICU</h3>
              <p class="text-sm text-blue-700 font-medium mt-0.5">Cedars-Sinai Medical Center</p>
            </div>
            <span class="bg-blue-50 text-blue-700 text-xs font-medium px-2.5 py-1 rounded-full border border-blue-100">Full-time</span>
          </div>
          <div class="mt-3 flex items-center gap-1.5 text-sm text-slate-600">
            <svg class="w-4 h-4 text-slate-400" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/></svg>
            <span>Los Angeles, CA</span>
          </div>
          <div class="mt-3 flex items-center gap-1.5 text-sm font-medium text-slate-800 bg-slate-50 rounded-lg px-3 py-2 w-fit">
            <span class="text-slate-500 text-xs">Salary</span> $120,000 – $145,000
          </div>
          <div class="mt-4 pt-3 border-t border-slate-100 flex items-center justify-between">
            <span class="text-xs text-slate-500">Posted 2 days ago</span>
            <button data-job="Registered Nurse – ICU at Cedars-Sinai" class="apply-btn bg-blue-700 hover:bg-blue-800 text-white text-sm font-medium px-4 py-2 rounded-xl transition-all duration-150 focus-visible:ring-2 focus-visible:ring-blue-500 focus-visible:ring-offset-1 shadow-sm">
              Apply Now
            </button>
          </div>
        </article>

        <!-- Job Card 2: Surgical Tech -->
        <article class="job-card bg-white rounded-2xl border border-slate-200 p-5 shadow-sm flex flex-col">
          <div class="flex items-start justify-between">
            <div>
              <h3 class="text-lg font-semibold text-slate-900 leading-snug">Surgical Technologist</h3>
              <p class="text-sm text-blue-700 font-medium mt-0.5">Mayo Clinic</p>
            </div>
            <span class="bg-blue-50 text-blue-700 text-xs font-medium px-2.5 py-1 rounded-full border border-blue-100">Full-time</span>
          </div>
          <div class="mt-3 flex items-center gap-1.5 text-sm text-slate-600">
            <svg class="w-4 h-4 text-slate-400" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/></svg>
            <span>Rochester, MN</span>
          </div>
          <div class="mt-3 flex items-center gap-1.5 text-sm font-medium text-slate-800 bg-slate-50 rounded-lg px-3 py-2 w-fit">
            <span class="text-slate-500 text-xs">Salary</span> $68,000 – $85,000
          </div>
          <div class="mt-4 pt-3 border-t border-slate-100 flex items-center justify-between">
            <span class="text-xs text-slate-500">Posted 5 days ago</span>
            <button data-job="Surgical Technologist at Mayo Clinic" class="apply-btn bg-blue-700 hover:bg-blue-800 text-white text-sm font-medium px-4 py-2 rounded-xl transition-all duration-150 focus-visible:ring-2 focus-visible:ring-blue-500 focus-visible:ring-offset-1 shadow-sm">
              Apply Now
            </button>
          </div>
        </article>

        <!-- Job Card 3: Administration -->
        <article class="job-card bg-white rounded-2xl border border-slate-200 p-5 shadow-sm flex flex-col">
          <div class="flex items-start justify-between">
            <div>
              <h3 class="text-lg font-semibold text-slate-900 leading-snug">Hospital Administrator</h3>
              <p class="text-sm text-blue-700 font-medium mt-0.5">Johns Hopkins Hospital</p>
            </div>
            <span class="bg-blue-50 text-blue-700 text-xs font-medium px-2.5 py-1 rounded-full border border-blue-100">Full-time</span>
          </div>
          <div class="mt-3 flex items-center gap-1.5 text-sm text-slate-600">
            <svg class="w-4 h-4 text-slate-400" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/></svg>
            <span>Baltimore, MD</span>
          </div>
          <div class="mt-3 flex items-center gap-1.5 text-sm font-medium text-slate-800 bg-slate-50 rounded-lg px-3 py-2 w-fit">
            <span class="text-slate-500 text-xs">Salary</span> $130,000 – $175,000
          </div>
          <div class="mt-4 pt-3 border-t border-slate-100 flex items-center justify-between">
            <span class="text-xs text-slate-500">Posted 1 week ago</span>
            <button data-job="Hospital Administrator at Johns Hopkins" class="apply-btn bg-blue-700 hover:bg-blue-800 text-white text-sm font-medium px-4 py-2 rounded-xl transition-all duration-150 focus-visible:ring-2 focus-visible:ring-blue-500 focus-visible:ring-offset-1 shadow-sm">
              Apply Now
            </button>
          </div>
        </article>

        <!-- Job Card 4: Radiologic Technologist -->
        <article class="job-card bg-white rounded-2xl border border-slate-200 p-5 shadow-sm flex flex-col">
          <div class="flex items-start justify-between">
            <div>
              <h3 class="text-lg font-semibold text-slate-900 leading-snug">Radiologic Technologist</h3>
              <p class="text-sm text-blue-700 font-medium mt-0.5">Cleveland Clinic</p>
            </div>
            <span class="bg-blue-50 text-blue-700 text-xs font-medium px-2.5 py-1 rounded-full border border-blue-100">Full-time</span>
          </div>
          <div class="mt-3 flex items-center gap-1.5 text-sm text-slate-600">
            <svg class="w-4 h-4 text-slate-400" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/></svg>
            <span>Cleveland, OH</span>
          </div>
          <div class="mt-3 flex items-center gap-1.5 text-sm font-medium text-slate-800 bg-slate-50 rounded-lg px-3 py-2 w-fit">
            <span class="text-slate-500 text-xs">Salary</span> $70,000 – $90,000
          </div>
          <div class="mt-4 pt-3 border-t border-slate-100 flex items-center justify-between">
            <span class="text-xs text-slate-500">Posted 3 days ago</span>
            <button data-job="Radiologic Technologist at Cleveland Clinic" class="apply-btn bg-blue-700 hover:bg-blue-800 text-white text-sm font-medium px-4 py-2 rounded-xl transition-all duration-150 focus-visible:ring-2 focus-visible:ring-blue-500 focus-visible:ring-offset-1 shadow-sm">
              Apply Now
            </button>
          </div>
        </article>

        <!-- Job Card 5: Nurse Practitioner -->
        <article class="job-card bg-white rounded-2xl border border-slate-200 p-5 shadow-sm flex flex-col">
          <div class="flex items-start justify-between">
            <div>
              <h3 class="text-lg font-semibold text-slate-900 leading-snug">Nurse Practitioner – Oncology</h3>
              <p class="text-sm text-blue-700 font-medium mt-0.5">MD Anderson Cancer Center</p>
            </div>
            <span class="bg-blue-50 text-blue-700 text-xs font-medium px-2.5 py-1 rounded-full border border-blue-100">Full-time</span>
          </div>
          <div class="mt-3 flex items-center gap-1.5 text-sm text-slate-600">
            <svg class="w-4 h-4 text-slate-400" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/></svg>
            <span>Houston, TX</span>
          </div>
          <div class="mt-3 flex items-center gap-1.5 text-sm font-medium text-slate-800 bg-slate-50 rounded-lg px-3 py-2 w-fit">
            <span class="text-slate-500 text-xs">Salary</span> $135,000 – $165,000
          </div>
          <div class="mt-4 pt-3 border-t border-slate-100 flex items-center justify-between">
            <span class="text-xs text-slate-500">Posted 1 day ago</span>
            <button data-job="Nurse Practitioner – Oncology at MD Anderson" class="apply-btn bg-blue-700 hover:bg-blue-800 text-white text-sm font-medium px-4 py-2 rounded-xl transition-all duration-150 focus-visible:ring-2 focus-visible:ring-blue-500 focus-visible:ring-offset-1 shadow-sm">
              Apply Now
            </button>
          </div>
        </article>

        <!-- Job Card 6: Physical Therapist -->
        <article class="job-card bg-white rounded-2xl border border-slate-200 p-5 shadow-sm flex flex-col">
          <div class="flex items-start justify-between">
            <div>
              <h3 class="text-lg font-semibold text-slate-900 leading-snug">Physical Therapist</h3>
              <p class="text-sm text-blue-700 font-medium mt-0.5">Massachusetts General Hospital</p>
            </div>
            <span class="bg-blue-50 text-blue-700 text-xs font-medium px-2.5 py-1 rounded-full border border-blue-100">Full-time</span>
          </div>
          <div class="mt-3 flex items-center gap-1.5 text-sm text-slate-600">
            <svg class="w-4 h-4 text-slate-400" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/></svg>
            <span>Boston, MA</span>
          </div>
          <div class="mt-3 flex items-center gap-1.5 text-sm font-medium text-slate-800 bg-slate-50 rounded-lg px-3 py-2 w-fit">
            <span class="text-slate-500 text-xs">Salary</span> $85,000 – $105,000
          </div>
          <div class="mt-4 pt-3 border-t border-slate-100 flex items-center justify-between">
            <span class="text-xs text-slate-500">Posted 4 days ago</span>
            <button data-job="Physical Therapist at Mass General" class="apply-btn bg-blue-700 hover:bg-blue-800 text-white text-sm font-medium px-4 py-2 rounded-xl transition-all duration-150 focus-visible:ring-2 focus-visible:ring-blue-500 focus-visible:ring-offset-1 shadow-sm">
              Apply Now
            </button>
          </div>
        </article>
      </div>
    </section>
  </main>

  <!-- ========== MODAL: PAYMENT GATEWAY SIMULATION ========== -->
  <!-- The modal is hidden by default. It becomes visible when an Apply button is clicked. -->
  <div id="paymentModal" class="fixed inset-0 z-50 hidden items-center justify-center p-4" role="dialog" aria-modal="true" aria-labelledby="modalTitle">
    <!-- Backdrop -->
    <div class="modal-backdrop absolute inset-0" onclick="closeModal()" aria-hidden="true"></div>
    
    <!-- Modal content -->
    <div class="modal-content relative bg-white rounded-2xl shadow-2xl max-w-lg w-full p-6 transition-all duration-200">
      <!-- Close button -->
      <button onclick="closeModal()" class="absolute top-4 right-4 text-slate-400 hover:text-slate-600 focus-visible:ring-2 rounded-full p-1" aria-label="Close application modal">
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/></svg>
      </button>

      <!-- Modal header -->
      <div class="mb-4">
        <h2 id="modalTitle" class="text-xl font-bold text-slate-900">Secure application</h2>
        <p id="jobContext" class="text-sm text-slate-600 mt-1">Applying for: <span class="font-medium text-blue-700">Registered Nurse – ICU</span></p>
      </div>

      <!-- Payment section -->
      <div class="bg-slate-50 rounded-xl p-4 border border-slate-200">
        <div class="flex items-center justify-between mb-3">
          <span class="text-sm font-medium text-slate-700">Application fee</span>
          <span class="text-lg font-bold text-slate-900">$49.00</span>
        </div>
        <p class="text-xs text-slate-500 mb-4">One-time verification fee. Secure & encrypted.</p>

        <!-- Mock payment form (fields are for simulation only) -->
        <div class="space-y-3">
          <div>
            <label for="cardNumber" class="block text-xs font-medium text-slate-600 mb-1">Card number</label>
            <input id="cardNumber" type="text" placeholder="4242 4242 4242 4242" value="4242 4242 4242 4242" class="w-full px-3 py-2 bg-white border border-slate-300 rounded-lg text-sm focus:ring-2 focus:ring-blue-500 focus:border-blue-500 outline-none" readonly>
          </div>
          <div class="grid grid-cols-2 gap-3">
            <div>
              <label for="expiry" class="block text-xs font-medium text-slate-600 mb-1">Expiry</label>
              <input id="expiry" type="text" placeholder="MM/YY" value="12/28" class="w-full px-3 py-2 bg-white border border-slate-300 rounded-lg text-sm focus:ring-2 focus:ring-blue-500 focus:border-blue-500 outline-none" readonly>
            </div>
            <div>
              <label for="cvc" class="block text-xs font-medium text-slate-600 mb-1">CVC</label>
              <input id="cvc" type="text" placeholder="123" value="123" class="w-full px-3 py-2 bg-white border border-slate-300 rounded-lg text-sm focus:ring-2 focus:ring-blue-500 focus:border-blue-500 outline-none" readonly>
            </div>
          </div>
        </div>

        <!-- Pay button (enabled by default, but triggers payment processing) -->
        <button id="payButton" class="mt-4 w-full bg-blue-700 hover:bg-blue-800 text-white font-medium py-2.5 rounded-xl transition-all duration-150 focus-visible:ring-2 focus-visible:ring-blue-500 focus-visible:ring-offset-1 shadow-sm flex items-center justify-center gap-2">
          <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 10h18M7 15h1m4 0h1m-7 4h12a3 3 0 003-3V8a3 3 0 00-3-3H6a3 3 0 00-3 3v8a3 3 0 003 3z"/></svg>
          Pay $49.00 & continue
        </button>

        <!-- Payment success message (hidden initially) -->
        <div id="paymentSuccessMessage" class="mt-3 hidden payment-success bg-green-50 border border-green-200 text-green-800 text-sm p-3 rounded-xl flex items-start gap-2">
          <svg class="w-5 h-5 text-green-600 shrink-0 mt-0.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
          <span>Payment successful! You can now submit your application.</span>
        </div>
      </div>

      <!-- Submit application button (disabled until payment succeeds) -->
      <button id="submitApplicationBtn" disabled class="mt-4 w-full bg-slate-300 text-slate-600 font-medium py-2.5 rounded-xl cursor-not-allowed transition-all duration-150 btn-disabled" aria-disabled="true">
        Submit Application
      </button>
      <p class="text-[11px] text-slate-400 text-center mt-3">By proceeding you agree to our terms. This is a demo payment simulation.</p>
    </div>
  </div>

  <!-- ========== SUCCESS TOAST (floating notification) ========== -->
  <div id="toastNotification" class="fixed bottom-6 left-1/2 -translate-x-1/2 z-50 bg-slate-900 text-white px-6 py-3 rounded-full shadow-xl text-sm font-medium hidden items-center gap-2">
    <svg class="w-5 h-5 text-green-400" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
    Application submitted successfully! 🎉
  </div>

  <!-- ========== JAVASCRIPT: MODAL + PAYMENT LOGIC ========== -->
  <script>
    (function() {
      // ----- DOM references -----
      const modal = document.getElementById('paymentModal');
      const jobContextSpan = document.querySelector('#jobContext span');
      const payButton = document.getElementById('payButton');
      const paymentSuccessMessage = document.getElementById('paymentSuccessMessage');
      const submitApplicationBtn = document.getElementById('submitApplicationBtn');
      const toast = document.getElementById('toastNotification');
      const applyButtons = document.querySelectorAll('.apply-btn');

      // Payment state
      let paymentCompleted = false;

      // ----- Helper: open modal with job context -----
      function openModal(jobTitle) {
        jobContextSpan.textContent = jobTitle;
        modal.classList.remove('hidden');
        modal.classList.add('flex');
        // Reset payment state each time modal opens
        resetPaymentState();
        // Focus first focusable element (accessibility)
        payButton.focus();
      }

      // ----- Helper: close modal -----
      window.closeModal = function() {
        modal.classList.add('hidden');
        modal.classList.remove('flex');
        resetPaymentState();
      };

      // ----- Reset payment simulation state -----
      function resetPaymentState() {
        paymentCompleted = false;
        paymentSuccessMessage.classList.add('hidden');
        submitApplicationBtn.disabled = true;
        submitApplicationBtn.classList.add('btn-disabled', 'bg-slate-300', 'text-slate-600', 'cursor-not-allowed');
        submitApplicationBtn.classList.remove('bg-green-700', 'hover:bg-green-800', 'text-white', 'cursor-pointer', 'shadow-sm');
        // Reset pay button to enabled state
        payButton.disabled = false;
        payButton.classList.remove('opacity-50', 'pointer-events-none');
        payButton.innerHTML = `<svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 10h18M7 15h1m4 0h1m-7 4h12a3 3 0 003-3V8a3 3 0 00-3-3H6a3 3 0 00-3 3v8a3 3 0 003 3z"/></svg> Pay $49.00 & continue`;
      }

      // ----- Simulate payment processing -----
      function processPayment() {
        if (paymentCompleted) return;

        // Visual feedback: disable pay button while "processing"
        payButton.disabled = true;
        payButton.classList.add('opacity-70', 'pointer-events-none');
        payButton.innerHTML = `<svg class="animate-spin w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><circle cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4" stroke-opacity="0.25"/><path fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"/></svg> Processing...`;

        // Simulate network delay (1.2s)
        setTimeout(() => {
          paymentCompleted = true;
          // Show success message
          paymentSuccessMessage.classList.remove('hidden');
          // Enable submit application button
          submitApplicationBtn.disabled = false;
          submitApplicationBtn.classList.remove('btn-disabled', 'bg-slate-300', 'text-slate-600', 'cursor-not-allowed');
          submitApplicationBtn.classList.add('bg-green-700', 'hover:bg-green-800', 'text-white', 'cursor-pointer', 'shadow-sm');
          // Update pay button to show paid
          payButton.innerHTML = `<svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"/></svg> Payment successful`;
          payButton.classList.add('bg-green-100', 'text-green-800', 'border', 'border-green-200');
          payButton.classList.remove('bg-blue-700', 'hover:bg-blue-800', 'text-white');
          payButton.disabled = true; // keep disabled after success
        }, 1200);
      }

      // ----- Handle application submission (only after payment) -----
      function handleSubmitApplication() {
        if (!paymentCompleted) return;
        // Show success toast
        toast.classList.remove('hidden');
        toast.classList.add('flex');
        // Close modal after short delay
        setTimeout(() => {
          closeModal();
          // Hide toast after 4 seconds
          setTimeout(() => {
            toast.classList.add('hidden');
            toast.classList.remove('flex');
          }, 4000);
        }, 600);
      }

      // ----- Attach event listeners to all apply buttons -----
      applyButtons.forEach(btn => {
        btn.addEventListener('click', function(e) {
          e.preventDefault();
          const jobTitle = this.getAttribute('data-job') || 'Healthcare position';
          openModal(jobTitle);
        });
      });

      // Pay button click
      payButton.addEventListener('click', processPayment);

      // Submit application click
      submitApplicationBtn.addEventListener('click', handleSubmitApplication);

      // Close modal on Escape key
      document.addEventListener('keydown', function(e) {
        if (e.key === 'Escape' && !modal.classList.contains('hidden')) {
          closeModal();
        }
      });

      // Accessibility: trap focus within modal when open (simple implementation)
      modal.addEventListener('keydown', function(e) {
        if (e.key === 'Tab') {
          const focusable = modal.querySelectorAll('button:not([disabled]), input:not([readonly]), [href]');
          const first = focusable[0];
          const last = focusable[focusable.length - 1];
          if (e.shiftKey && document.activeElement === first) {
            e.preventDefault();
            last.focus();
          } else if (!e.shiftKey && document.activeElement === last) {
            e.preventDefault();
            first.focus();
          }
        }
      });

    })();
  </script>

  <!-- ========== FOOTER (minimal, clean) ========== -->
  <footer class="border-t border-slate-200 bg-white mt-8">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-6 text-center sm:text-left text-sm text-slate-500 flex flex-col sm:flex-row justify-between items-center gap-2">
      <p>© 2025 MediCareers — Trusted healthcare recruitment.</p>
      <div class="flex gap-4">
        <a href="#" class="hover:text-blue-700 transition-colors">Privacy</a>
        <a href="#" class="hover:text-blue-700 transition-colors">Terms</a>
        <a href="#" class="hover:text-blue-700 transition-colors">Support</a>
      </div>
    </div>
  </footer>

</body>
</html>
