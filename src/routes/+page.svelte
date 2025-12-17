<script lang="ts">
	import { onMount } from 'svelte';

    // Data for sections
    const navLinks = ["How it works", "Research", "Pricing"];
    
    // Logos removed for MVP - will add Swedish schools later

    const features = [
        {
            tag: "DAILY CHECK-INS",
            title: "Identify struggling students automatically",
            image: "phone",
            color: "bg-gray-100"
        },
        {
            tag: "AUTOMATED INTERVENTIONS",
            title: "Tier 2-3 support delivered during class",
            image: "video",
            color: "bg-gray-100"
        },
        {
            tag: "RTI TRACKING",
            title: "Zero paperwork, complete documentation",
            image: "analytics",
            color: "bg-gray-100"
        },
        {
            tag: "CURRICULUM-MAPPED",
            title: "Follows Swedish math curriculum, Years 1-12",
            image: "editor",
            color: "bg-gray-100"
        },
        {
            tag: "RESEARCH-BASED",
            title: "Explicit instruction with gradual release",
            image: "search",
            color: "bg-gray-100"
        },
        {
            tag: "PRIVACY-FIRST",
            title: "GDPR compliant, no PII stored",
            image: "admin",
            color: "bg-gray-100"
        }
    ];

    const testimonials = [
        {
            quote: "Jenny has completely eliminated my RTI paperwork. I finally have time to actually teach instead of documenting everything manually.",
            name: "Anna Bergström",
            role: "Math teacher, Year 4",
            avatar: "AB"
        },
        {
            quote: "I can instantly see which students need Tier 2 support. No more guessing or waiting weeks to identify struggling students.",
            name: "Erik Lindqvist",
            role: "Mathematics teacher, Years 7-9",
            avatar: "EL"
        },
         {
            quote: "The daily check-ins take 2 minutes, and I get complete RTI documentation automatically. It's exactly what Swedish teachers have been waiting for.",
            name: "Sofia Andersson",
            role: "Math teacher, Year 6",
            avatar: "SA"
        },
        {
            quote: "My students get help during class without missing instruction. Jenny delivers interventions that actually follow our curriculum.",
            name: "Lars Johansson",
            role: "Mathematics teacher, Years 4-6",
            avatar: "LJ"
        },
        {
            quote: "I was worried about GDPR compliance, but Jenny doesn't store any student names or personal information. Complete peace of mind.",
            name: "Maria Nilsson",
            role: "Math teacher, Year 3",
            avatar: "MN"
        },
        {
            quote: "Christian and Olle walked me through everything personally. Within a week, my entire class was using it. The easiest implementation I've experienced.",
            name: "Johan Karlsson",
            role: "Mathematics teacher, Years 1-3",
            avatar: "JK"
        }
    ];

    const partnershipServices = [
        "Personal onboarding by founders",
        "Free trial until end of school year",
        "Complete implementation support",
        "Teacher training and resources",
        "Ongoing technical support",
        "Curriculum mapping assistance",
        "Regular check-ins and optimization"
    ];

    const comparisons = [
        {
            tag: "STUDENT IDENTIFICATION",
            left: "Wait weeks for assessment results, schedule meetings, manually review student work to identify Tier 2 needs",
            right: "Daily check-ins automatically identify struggling students in real-time with specific concept gaps"
        },
        {
            tag: "PROGRESS MONITORING",
            left: "Manually collect data, fill out forms, maintain binders, schedule regular assessments",
            right: "Automatic tracking and documentation with zero paperwork, always RTI-compliant"
        },
        {
            tag: "INTERVENTION DELIVERY",
            left: "Pull students out of class, schedule separate sessions, create custom materials for each student",
            right: "Automated interventions delivered during class, curriculum-mapped, no pull-outs required"
        },
        {
            tag: "DOCUMENTATION",
            left: "Spend hours per week documenting interventions, maintaining records, preparing for meetings",
            right: "Complete RTI documentation generated automatically, ready for meetings and compliance"
        },
        {
            tag: "TIME REQUIRED",
            left: "20% of teaching time spent on RTI paperwork and manual tracking",
            right: "2 minutes per day for check-ins, everything else automated"
        }
    ];

    const faqs = [
        "How does Jenny identify struggling students?",
        "Is Jenny GDPR compliant?",
        "What grades and curriculum does Jenny cover?",
        "How long does implementation take?",
        "Do students need to be pulled out of class?",
        "How much time do daily check-ins take?",
        "What research supports Jenny's methods?",
        "How does the free trial work?",
        "What happens to student data?"
    ];

</script>

<div class="font-sans text-gray-900 bg-white selection:bg-primary-200 selection:text-black">
    <!-- Navbar -->
    <nav class="sticky top-0 z-50 bg-white/80 backdrop-blur-md border-b border-gray-100">
        <div class="max-w-[1400px] mx-auto px-6 h-16 flex items-center justify-between">
            <div class="flex items-center gap-2">
                <!-- Logo Mark -->
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="text-black">
                    <path fill-rule="evenodd" clip-rule="evenodd" d="M6.99251 12.196C6.85314 12.5757 6.62925 12.9208 6.33682 13.2067H6.33835C6.00191 13.5351 5.58566 13.7756 5.12816 13.9059C4.67065 14.0362 4.18671 14.0522 3.72118 13.9523C3.25564 13.8524 2.82357 13.64 2.46501 13.3345C2.10645 13.0291 1.83299 12.6406 1.66998 12.2051C1.50697 11.7696 1.45969 11.3012 1.5325 10.8432C1.60532 10.3852 1.79587 9.95244 2.08653 9.58516C2.37718 9.21781 2.75852 8.9277 3.1952 8.74177C3.63188 8.55585 4.10979 8.48002 4.58462 8.52142L4.57074 8.50792C5.0567 8.54782 5.54575 8.48407 6.00378 8.32124C6.4618 8.15846 6.87776 7.90043 7.2226 7.56521C7.56746 7.22998 7.83285 6.82564 8.00036 6.38041C8.16786 5.93517 8.23344 5.45976 8.1924 4.98737L8.20628 5.00087C8.15181 4.43594 8.27796 3.86844 8.56753 3.37575C8.85701 2.88307 9.29579 2.48919 9.82407 2.24782C10.3523 2.00645 10.9443 1.92933 11.5192 2.02701C12.0942 2.12467 12.6243 2.39237 13.037 2.79358C13.4497 3.19479 13.7251 3.70999 13.8256 4.26892C13.926 4.82785 13.8467 5.4033 13.5984 5.9168C13.3501 6.4303 12.9449 6.85685 12.4381 7.13828C11.9313 7.41971 11.3474 7.54233 10.7663 7.4894L10.781 7.5029C10.2949 7.46279 9.80563 7.52632 9.34741 7.68904C8.88919 7.85176 8.47309 8.10975 8.12805 8.44499C7.78301 8.78025 7.51742 9.18466 7.34983 9.63001C7.18224 10.0754 7.11669 10.551 7.15774 11.0235L7.14309 11.01C7.1833 11.4112 7.13189 11.8162 6.99251 12.196ZM11.5077 14.7121L11.493 14.6986C11.9061 14.739 12.3232 14.6897 12.7143 14.5543C13.1053 14.4188 13.4605 14.2007 13.7542 13.9154C14.0477 13.6302 14.2726 13.285 14.4121 12.905C14.5518 12.525 14.6028 12.1196 14.5615 11.718L14.5762 11.7315C14.5351 11.2591 14.6007 10.7838 14.7681 10.3385C14.9356 9.89327 15.2011 9.48893 15.5459 9.15368C15.8908 8.8185 16.3068 8.56042 16.7648 8.39767C17.2228 8.23481 17.7118 8.17111 18.1978 8.21099L18.1832 8.19749C18.7645 8.25059 19.3485 8.12801 19.8556 7.84656C20.3627 7.56511 20.7681 7.13845 21.0165 6.62479C21.265 6.11114 21.3444 5.53548 21.2439 4.97634C21.1435 4.4172 20.868 3.9018 20.4551 3.50044C20.0422 3.09909 19.512 2.8313 18.9368 2.73364C18.3616 2.63596 17.7695 2.71315 17.241 2.95467C16.7126 3.19618 16.2737 3.59027 15.9842 4.08319C15.6946 4.57609 15.5685 5.14383 15.6232 5.70895L15.6093 5.6947C15.6504 6.16712 15.585 6.64259 15.4175 7.08788C15.2501 7.53318 14.9846 7.93758 14.6398 8.27287C14.2949 8.60805 13.8789 8.86612 13.4208 9.02888C12.9627 9.19163 12.4736 9.25523 11.9876 9.21526L12.0015 9.22951C11.5885 9.18908 11.1713 9.23836 10.7803 9.37381C10.3893 9.50919 10.034 9.72744 9.74039 10.0127C9.44674 10.2979 9.22199 10.6431 9.08234 11.0231C8.94276 11.4031 8.89176 11.8085 8.93304 12.2101L8.91915 12.1966C8.96005 12.6689 8.89439 13.1443 8.72688 13.5895C8.5593 14.0346 8.29389 14.4389 7.94908 14.7741C7.60425 15.1093 7.18835 15.3673 6.73039 15.5302C6.27242 15.693 5.78342 15.7569 5.29749 15.7171L5.31138 15.7306C4.73003 15.6775 4.14599 15.8001 3.63892 16.0815C3.13186 16.363 2.72644 16.7896 2.478 17.3033C2.22954 17.817 2.15013 18.3926 2.25061 18.9518C2.35109 19.5109 2.62657 20.0263 3.03945 20.4276C3.45234 20.829 3.98253 21.0968 4.55773 21.1944C5.13293 21.2921 5.72512 21.2149 6.25353 20.9734C6.78193 20.7319 7.22085 20.3379 7.51038 19.8449C7.79994 19.352 7.92601 18.7843 7.87139 18.2191L7.88605 18.2326C7.845 17.7602 7.91058 17.2849 8.07809 16.8396C8.24551 16.3944 8.511 15.99 8.85581 15.6548C9.20069 15.3196 9.61664 15.0615 10.0746 14.8988C10.5327 14.7359 11.0217 14.6722 11.5077 14.7121ZM17.1996 10.7633C16.9071 11.0493 16.6832 11.3944 16.5437 11.7741C16.4042 12.1538 16.3526 12.5587 16.3925 12.9601L16.3786 12.9466C16.4197 13.419 16.3541 13.8944 16.1866 14.3396C16.0191 14.7849 15.7537 15.1892 15.4089 15.5244C15.064 15.8596 14.648 16.1177 14.19 16.2804C13.732 16.4433 13.2429 16.507 12.757 16.4671L12.7708 16.4806C12.1896 16.4281 11.6057 16.551 11.0989 16.8328C10.5921 17.1145 10.1871 17.5414 9.93902 18.0551C9.69097 18.5689 9.61188 19.1444 9.71265 19.7035C9.81349 20.2625 10.0892 20.7777 10.5022 21.1788C10.9152 21.5799 11.4454 21.8474 12.0205 21.9448C12.5957 22.0423 13.1877 21.9649 13.716 21.7234C14.2443 21.4817 14.683 21.0877 14.9724 20.5947C15.2618 20.1018 15.3878 19.5342 15.3332 18.9692L15.3478 18.9827C15.3068 18.5103 15.3723 18.0349 15.5398 17.5896C15.7073 17.1444 15.9728 16.7401 16.3176 16.4048C16.6625 16.0696 17.0784 15.8115 17.5364 15.6488C17.9945 15.486 18.4835 15.4222 18.9695 15.4621L18.9548 15.4486C19.4296 15.4901 19.9076 15.4144 20.3444 15.2286C20.7811 15.0427 21.1625 14.7527 21.4533 14.3854C21.744 14.0181 21.9347 13.5854 22.0075 13.1274C22.0805 12.6694 22.0332 12.2009 21.8703 11.7653C21.7073 11.3298 21.4339 10.9413 21.0754 10.6358C20.7168 10.3303 20.2848 10.1178 19.8192 10.0179C19.3536 9.91795 18.8697 9.93385 18.4121 10.0641C17.9546 10.1945 17.5383 10.4349 17.2019 10.7633H17.1996Z" fill="currentColor"/>
                </svg>
                <span class="font-medium text-lg tracking-tight">Jenny</span>
            </div>

            <div class="hidden md:flex items-center gap-8 text-sm font-medium text-gray-600">
                {#each navLinks as link}
                    <a href="#" class="hover:text-black transition-colors">{link}</a>
                {/each}
            </div>

            <button class="bg-black text-white px-5 py-2 rounded-full text-sm font-medium hover:bg-gray-800 transition-colors">
                Book a demo
            </button>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="pt-20 pb-16 px-6 text-center overflow-hidden">
        <div class="max-w-4xl mx-auto mb-12">
            <h1 class="font-serif text-6xl md:text-7xl lg:text-[5rem] leading-[1.1] mb-6 font-normal tracking-tight">
                Know exactly who <br/> needs help
            </h1>
            <p class="text-lg md:text-xl text-gray-600 max-w-2xl mx-auto mb-8 leading-relaxed">
                Jenny identifies struggling students through daily check-ins and delivers automated, individualized math interventions during class.
            </p>
            <button class="bg-black text-white px-8 py-3 rounded-full text-base font-medium hover:bg-gray-800 transition-colors">
                Book a demo
            </button>
        </div>

        <!-- Hero Image Collage Mockup -->
        <div class="relative max-w-[1400px] mx-auto h-[400px] md:h-[600px] mt-12 select-none pointer-events-none">
            <!-- We will build a CSS composition of screens -->
            <div class="relative w-full h-full flex justify-center items-end">
                
                <!-- Left Laptop -->
                <div class="absolute left-[-10%] bottom-0 w-[60%] md:w-[45%] z-10 transform -translate-x-10 translate-y-10">
                     <div class="bg-gray-900 rounded-t-xl p-1 shadow-2xl border border-gray-800 aspect-[16/10] overflow-hidden">
                        <!-- Screen Content -->
                        <div class="bg-gray-800 w-full h-full rounded-lg relative overflow-hidden">
                            <div class="absolute inset-0 bg-gradient-to-br from-blue-900 to-black opacity-80"></div>
                            <div class="p-4 text-white">
                                <div class="text-xs text-gray-400 mb-2">Space Tech</div>
                                <div class="h-2 w-20 bg-gray-600 rounded mb-4"></div>
                                <div class="grid grid-cols-2 gap-4">
                                    <div class="h-20 bg-gray-700/50 rounded"></div>
                                    <div class="h-20 bg-gray-700/50 rounded"></div>
                                </div>
                            </div>
                        </div>
                     </div>
                </div>

                <!-- Center Laptop (Main) -->
                <div class="absolute bottom-0 z-20 w-[70%] md:w-[50%] transform translate-y-5">
                    <div class="bg-black rounded-t-2xl p-2 shadow-2xl border border-gray-800 aspect-[16/10]">
                        <div class="bg-white w-full h-full rounded-xl overflow-hidden relative">
                            <!-- Mock UI -->
                            <div class="flex h-full">
                                <div class="w-1/3 bg-gray-50 p-4 border-r border-gray-100">
                                    <div class="h-8 w-8 bg-gray-200 rounded-full mb-4"></div>
                                    <div class="h-2 w-20 bg-gray-200 rounded mb-2"></div>
                                    <div class="h-2 w-16 bg-gray-200 rounded mb-6"></div>
                                    <div class="space-y-2">
                                        <div class="h-8 w-full bg-white border border-gray-200 rounded shadow-sm"></div>
                                        <div class="h-8 w-full bg-transparent rounded"></div>
                                    </div>
                                </div>
                                <div class="w-2/3 p-4">
                                    <div class="h-32 bg-gray-100 rounded-lg mb-4 flex items-center justify-center">
                                        <div class="w-12 h-12 bg-gray-300 rounded-full"></div>
                                    </div>
                                    <div class="h-4 w-3/4 bg-gray-100 rounded mb-2"></div>
                                    <div class="h-4 w-1/2 bg-gray-100 rounded"></div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Right Phone/Tablet -->
                <div class="absolute right-[-5%] bottom-10 w-[25%] md:w-[15%] z-30 transform translate-x-5">
                    <div class="bg-black rounded-[2rem] p-2 shadow-2xl border border-gray-800 aspect-[9/19]">
                        <div class="bg-white w-full h-full rounded-[1.5rem] overflow-hidden p-2 flex flex-col">
                             <div class="h-4 w-20 bg-gray-100 rounded mx-auto mb-4 mt-2"></div>
                             <div class="flex-1 bg-gray-50 rounded-xl p-2">
                                <div class="h-16 bg-primary-100 rounded-lg mb-2"></div>
                                <div class="h-16 bg-gray-100 rounded-lg mb-2"></div>
                             </div>
                        </div>
                    </div>
                </div>

                 <!-- Another Right Screen (Tablet?) -->
                <div class="absolute right-[10%] bottom-0 w-[40%] md:w-[30%] z-10 transform translate-x-10 translate-y-10">
                     <div class="bg-white rounded-t-xl p-1 shadow-2xl border border-gray-200 aspect-[4/3] overflow-hidden">
                        <div class="bg-gray-50 w-full h-full rounded-lg p-3">
                             <div class="flex gap-2 mb-3">
                                <div class="w-1/3 h-20 bg-white shadow-sm rounded-lg"></div>
                                <div class="w-1/3 h-20 bg-white shadow-sm rounded-lg"></div>
                                <div class="w-1/3 h-20 bg-white shadow-sm rounded-lg"></div>
                             </div>
                             <div class="h-32 bg-white shadow-sm rounded-lg"></div>
                        </div>
                     </div>
                </div>

            </div>
        </div>
    </section>

    <!-- Trust Section -->
    <section class="py-16 border-b border-gray-100">
        <div class="max-w-[1400px] mx-auto px-6 text-center">
            <p class="text-sm text-gray-500 mb-4">Built for Swedish math teachers, Years 1-12</p>
            <div class="flex flex-wrap justify-center items-center gap-8 text-xs text-gray-400">
                <div class="flex items-center gap-2">
                    <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>
                    GDPR Compliant
                </div>
                <div class="flex items-center gap-2">
                    <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>
                    Swedish Curriculum
                </div>
                <div class="flex items-center gap-2">
                    <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>
                    Research-Based
                </div>
                <div class="flex items-center gap-2">
                    <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>
                    Free Trial
                </div>
            </div>
        </div>
    </section>

    <!-- How Jenny Works Grid -->
    <section class="py-24 px-6 bg-gray-50">
        <div class="max-w-[1400px] mx-auto">
            <div class="text-center max-w-3xl mx-auto mb-20">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">How Jenny works</h2>
                <p class="text-lg text-gray-600 leading-relaxed">
                    Jenny eliminates RTI paperwork while ensuring every struggling student gets the support they need. Automated tracking, curriculum-mapped interventions, and zero pull-outs.
                </p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                {#each features as feature}
                    <div class="group bg-white rounded-2xl overflow-hidden shadow-sm hover:shadow-md transition-shadow duration-300 flex flex-col h-[500px]">
                        <div class="p-8 pb-0 flex-1">
                            <span class="inline-block bg-primary-100 text-primary-800 text-[10px] font-bold tracking-wider px-2 py-1 rounded mb-4 uppercase">
                                {feature.tag}
                            </span>
                            <h3 class="font-serif text-2xl leading-tight mb-4">
                                {feature.title}
                            </h3>
                        </div>
                        <div class="h-[300px] bg-gray-100 relative overflow-hidden mt-4 mx-4 rounded-t-xl group-hover:translate-y-[-5px] transition-transform duration-500">
                            <!-- Mockup Content based on type -->
                            {#if feature.image === 'phone'}
                                <div class="absolute bottom-[-20px] left-1/2 transform -translate-x-1/2 w-[180px] h-[350px] bg-black rounded-[2rem] border-4 border-black shadow-xl overflow-hidden">
                                     <div class="bg-white w-full h-full p-3 pt-8">
                                        <div class="h-2 w-12 bg-gray-200 rounded mx-auto mb-4"></div>
                                        <div class="space-y-2">
                                            <div class="h-16 bg-gray-50 rounded-lg"></div>
                                            <div class="h-16 bg-gray-50 rounded-lg"></div>
                                        </div>
                                     </div>
                                </div>
                            {:else if feature.image === 'video'}
                                <div class="absolute inset-0 p-4 flex items-end justify-center">
                                    <div class="w-full h-[90%] bg-gray-800 rounded-t-lg shadow-lg relative overflow-hidden">
                                        <div class="absolute inset-0 flex items-center justify-center text-white/20">
                                            <svg width="48" height="48" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 14.5v-9l6 4.5-6 4.5z"/></svg>
                                        </div>
                                        <div class="absolute bottom-4 left-4 flex gap-2">
                                            <div class="w-8 h-8 bg-gray-600 rounded-full"></div>
                                            <div class="w-8 h-8 bg-gray-600 rounded-full"></div>
                                        </div>
                                    </div>
                                </div>
                            {:else if feature.image === 'search'}
                                 <div class="absolute bottom-[-40px] right-[-20px] w-full h-full bg-white shadow-lg rounded-tl-2xl p-6 border border-gray-100">
                                     <div class="flex items-center gap-3 mb-4 border-b pb-4">
                                         <div class="w-8 h-8 bg-sana-lime rounded-full"></div>
                                         <div class="h-2 w-32 bg-gray-200 rounded"></div>
                                     </div>
                                     <div class="space-y-3">
                                         <div class="h-2 w-full bg-gray-100 rounded"></div>
                                         <div class="h-2 w-5/6 bg-gray-100 rounded"></div>
                                         <div class="h-2 w-4/6 bg-gray-100 rounded"></div>
                                     </div>
                                 </div>
                            {:else}
                                <div class="absolute inset-4 bg-white shadow-sm rounded-lg border border-gray-100 flex items-center justify-center">
                                    <div class="text-gray-300">UI Mockup</div>
                                </div>
                            {/if}
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section class="py-24 px-6 bg-white">
        <div class="max-w-[1400px] mx-auto">
            <div class="text-center max-w-3xl mx-auto mb-20">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">Loved by Swedish <br/> math teachers</h2>
                <p class="text-lg text-gray-600 leading-relaxed">
                    Finally, an RTI solution that saves time instead of creating more work. <br/> Hear from teachers using Jenny in their classrooms.
                </p>
            </div>

            <div class="columns-1 md:columns-2 lg:columns-3 gap-6 space-y-6">
                {#each testimonials as testimonial}
                    <div class="break-inside-avoid bg-gray-50 p-8 rounded-2xl">
                        <p class="text-lg leading-relaxed mb-6">"{testimonial.quote}"</p>
                        <div class="flex items-center gap-3">
                            <div class="w-10 h-10 bg-gray-300 rounded-full flex items-center justify-center text-sm font-bold text-gray-600">
                                {testimonial.avatar}
                            </div>
                            <div>
                                <div class="font-medium">{testimonial.name}</div>
                                <div class="text-sm text-gray-500">{testimonial.role}</div>
                            </div>
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <!-- Partnership Section -->
    <section class="py-24 px-6 bg-white border-t border-gray-100">
        <div class="max-w-[1400px] mx-auto">
             <div class="text-center max-w-3xl mx-auto mb-20">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">White-glove <br/> onboarding</h2>
                <p class="text-lg text-gray-600 leading-relaxed">
                    Christian and Olle personally guide every teacher through setup. <br/> You'll never feel alone in the implementation process.
                </p>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                <div class="bg-gray-50 p-12 rounded-3xl h-full">
                    <h3 class="font-serif text-2xl mb-8">What's included</h3>
                    <ul class="space-y-4">
                        {#each partnershipServices as service}
                            <li class="flex items-center gap-3">
                                <div class="w-5 h-5 rounded-full bg-primary-600 flex items-center justify-center shrink-0">
                                    <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="4" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>
                                </div>
                                <span class="text-gray-700">{service}</span>
                            </li>
                        {/each}
                    </ul>
                </div>
                <div class="h-full min-h-[500px] rounded-3xl overflow-hidden relative">
                    <!-- Image of founders with teacher -->
                    <div class="absolute inset-0 bg-gray-200">
                        <img src="/generated/image-two-founders-christian-and-olle-collabor-1765981675623-1.webp" alt="Founders Christian and Olle working with teacher" class="w-full h-full object-cover" />
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Comparison Section -->
    <section class="py-24 px-6 bg-white">
        <div class="max-w-[1400px] mx-auto">
             <div class="text-center max-w-3xl mx-auto mb-20">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">Traditional RTI <br/> vs Jenny</h2>
                <p class="text-lg text-gray-600 leading-relaxed">
                    See how Jenny eliminates the time-consuming manual work <br/> while improving student outcomes.
                </p>
            </div>

            <div class="border-t border-gray-100">
                <div class="grid grid-cols-3 py-4 text-xs text-gray-400 uppercase tracking-wider border-b border-gray-100">
                    <div>Traditional RTI</div>
                    <div class="text-center">→</div>
                    <div>Jenny</div>
                </div>
                {#each comparisons as item}
                    <div class="grid grid-cols-1 md:grid-cols-[1fr_auto_1fr] gap-8 py-12 border-b border-gray-100 items-center group hover:bg-gray-50 transition-colors px-4 -mx-4 rounded-xl">
                        <div class="text-gray-500 leading-relaxed md:pr-8">
                            {item.left}
                        </div>
                        <div class="flex justify-center">
                            <span class="bg-primary-100 text-primary-800 text-[10px] font-bold tracking-wider px-2 py-1 rounded uppercase whitespace-nowrap">
                                {item.tag}
                            </span>
                        </div>
                        <div class="text-black font-medium leading-relaxed md:pl-8">
                            {item.right}
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <!-- Privacy & Curriculum Section -->
    <section class="py-24 px-6 bg-white">
        <div class="max-w-[1400px] mx-auto">
             <div class="text-center max-w-3xl mx-auto mb-20">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">Privacy-first <br/> by design</h2>
                <p class="text-lg text-gray-600 leading-relaxed">
                    Built for Swedish schools with GDPR compliance from day one.
                </p>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-2 gap-16">
                <!-- Privacy -->
                <div>
                    <div class="text-center mb-8">
                        <span class="bg-primary-100 text-primary-800 text-[10px] font-bold tracking-wider px-2 py-1 rounded uppercase">
                            GDPR COMPLIANT FROM DAY ONE
                        </span>
                    </div>
                    <div class="space-y-4">
                        {#each ['No PII stored anywhere', 'Auto-generated usernames only', 'No student names or emails', 'Full data transparency', 'Swedish data residency', 'Complete audit trail'] as item}
                            <div class="bg-gray-50 rounded-xl p-6 hover:bg-gray-100 transition-colors">
                                <div class="flex items-center gap-3">
                                    <div class="w-6 h-6 rounded-full bg-primary-600 flex items-center justify-center shrink-0">
                                        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>
                                    </div>
                                    <span class="text-sm text-gray-700 font-medium">{item}</span>
                                </div>
                            </div>
                        {/each}
                    </div>
                </div>

                <!-- Curriculum -->
                <div>
                    <div class="text-center mb-8">
                        <span class="bg-primary-100 text-primary-800 text-[10px] font-bold tracking-wider px-2 py-1 rounded uppercase">
                            SWEDISH CURRICULUM MAPPED
                        </span>
                    </div>
                    <div class="space-y-4">
                         {#each ['Years 1-12 coverage', 'Aligned to Lgr22', 'All math concepts mapped', 'Prerequisite tracking', 'Research-based methods', 'Continuous updates'] as item}
                            <div class="bg-gray-50 rounded-xl p-6 hover:bg-gray-100 transition-colors">
                                <div class="flex items-center gap-3">
                                    <div class="w-6 h-6 rounded-full bg-primary-600 flex items-center justify-center shrink-0">
                                        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>
                                    </div>
                                    <span class="text-sm text-gray-700 font-medium">{item}</span>
                                </div>
                            </div>
                        {/each}
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Mission Section -->
    <section class="py-24 px-6">
        <div class="max-w-[1400px] mx-auto grid grid-cols-1 lg:grid-cols-2 min-h-[600px] gap-0">
            <div class="bg-white relative flex items-center justify-center p-12 overflow-hidden">
                <img src="/generated/image-swedish-elementary-school-students-worki-1765981697252-2.webp" alt="Students learning math" class="w-full h-full object-cover absolute inset-0" />
            </div>
            <div class="bg-gray-950 p-12 lg:p-24 flex flex-col justify-center text-white">
                <p class="font-serif text-3xl md:text-4xl leading-tight mb-8">
                    Jenny was built by Christian and Olle to solve a problem every Swedish math teacher faces: too much RTI paperwork, not enough time to actually teach.
                </p>
                <p class="font-serif text-3xl md:text-4xl leading-tight">
                    We believe every struggling student deserves immediate, research-backed support—without pulling them out of class or burying teachers in documentation.
                </p>
            </div>
        </div>
    </section>

    <!-- Bottom CTA -->
    <section class="py-32 px-6 text-center bg-white">
        <div class="max-w-4xl mx-auto">
            <h2 class="font-serif text-6xl md:text-7xl mb-6">Start your free trial</h2>
            <p class="text-xl text-gray-600 mb-10">Free until the end of the school year. Talk to Christian or Olle to get started.</p>
            <button class="bg-black text-white px-8 py-3 rounded-full text-base font-medium hover:bg-gray-800 transition-colors">
                Book a demo
            </button>
        </div>
    </section>

    <!-- FAQ Section -->
    <section class="py-24 px-6 bg-white border-t border-gray-100">
        <div class="max-w-[1400px] mx-auto">
            <h2 class="font-serif text-5xl mb-16">FAQ</h2>
            <div class="space-y-4">
                {#each faqs as faq}
                    <div class="border-b border-gray-100 py-6 flex justify-between items-center cursor-pointer group hover:bg-gray-50 px-4 -mx-4 rounded-lg transition-colors">
                        <span class="text-lg font-medium">{faq}</span>
                        <div class="w-8 h-8 rounded-full bg-black text-white flex items-center justify-center group-hover:bg-gray-800 transition-colors">
                            <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><line x1="12" y1="5" x2="12" y2="19"></line><line x1="5" y1="12" x2="19" y2="12"></line></svg>
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="py-24 px-6 bg-white border-t border-gray-100">
        <div class="max-w-[1400px] mx-auto grid grid-cols-1 md:grid-cols-4 gap-12">
            <div class="col-span-1 md:col-span-1">
                <div class="flex items-center gap-2 mb-8">
                     <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="text-black">
                        <path fill-rule="evenodd" clip-rule="evenodd" d="M6.99251 12.196C6.85314 12.5757 6.62925 12.9208 6.33682 13.2067H6.33835C6.00191 13.5351 5.58566 13.7756 5.12816 13.9059C4.67065 14.0362 4.18671 14.0522 3.72118 13.9523C3.25564 13.8524 2.82357 13.64 2.46501 13.3345C2.10645 13.0291 1.83299 12.6406 1.66998 12.2051C1.50697 11.7696 1.45969 11.3012 1.5325 10.8432C1.60532 10.3852 1.79587 9.95244 2.08653 9.58516C2.37718 9.21781 2.75852 8.9277 3.1952 8.74177C3.63188 8.55585 4.10979 8.48002 4.58462 8.52142L4.57074 8.50792C5.0567 8.54782 5.54575 8.48407 6.00378 8.32124C6.4618 8.15846 6.87776 7.90043 7.2226 7.56521C7.56746 7.22998 7.83285 6.82564 8.00036 6.38041C8.16786 5.93517 8.23344 5.45976 8.1924 4.98737L8.20628 5.00087C8.15181 4.43594 8.27796 3.86844 8.56753 3.37575C8.85701 2.88307 9.29579 2.48919 9.82407 2.24782C10.3523 2.00645 10.9443 1.92933 11.5192 2.02701C12.0942 2.12467 12.6243 2.39237 13.037 2.79358C13.4497 3.19479 13.7251 3.70999 13.8256 4.26892C13.926 4.82785 13.8467 5.4033 13.5984 5.9168C13.3501 6.4303 12.9449 6.85685 12.4381 7.13828C11.9313 7.41971 11.3474 7.54233 10.7663 7.4894L10.781 7.5029C10.2949 7.46279 9.80563 7.52632 9.34741 7.68904C8.88919 7.85176 8.47309 8.10975 8.12805 8.44499C7.78301 8.78025 7.51742 9.18466 7.34983 9.63001C7.18224 10.0754 7.11669 10.551 7.15774 11.0235L7.14309 11.01C7.1833 11.4112 7.13189 11.8162 6.99251 12.196ZM11.5077 14.7121L11.493 14.6986C11.9061 14.739 12.3232 14.6897 12.7143 14.5543C13.1053 14.4188 13.4605 14.2007 13.7542 13.9154C14.0477 13.6302 14.2726 13.285 14.4121 12.905C14.5518 12.525 14.6028 12.1196 14.5615 11.718L14.5762 11.7315C14.5351 11.2591 14.6007 10.7838 14.7681 10.3385C14.9356 9.89327 15.2011 9.48893 15.5459 9.15368C15.8908 8.8185 16.3068 8.56042 16.7648 8.39767C17.2228 8.23481 17.7118 8.17111 18.1978 8.21099L18.1832 8.19749C18.7645 8.25059 19.3485 8.12801 19.8556 7.84656C20.3627 7.56511 20.7681 7.13845 21.0165 6.62479C21.265 6.11114 21.3444 5.53548 21.2439 4.97634C21.1435 4.4172 20.868 3.9018 20.4551 3.50044C20.0422 3.09909 19.512 2.8313 18.9368 2.73364C18.3616 2.63596 17.7695 2.71315 17.241 2.95467C16.7126 3.19618 16.2737 3.59027 15.9842 4.08319C15.6946 4.57609 15.5685 5.14383 15.6232 5.70895L15.6093 5.6947C15.6504 6.16712 15.585 6.64259 15.4175 7.08788C15.2501 7.53318 14.9846 7.93758 14.6398 8.27287C14.2949 8.60805 13.8789 8.86612 13.4208 9.02888C12.9627 9.19163 12.4736 9.25523 11.9876 9.21526L12.0015 9.22951C11.5885 9.18908 11.1713 9.23836 10.7803 9.37381C10.3893 9.50919 10.034 9.72744 9.74039 10.0127C9.44674 10.2979 9.22199 10.6431 9.08234 11.0231C8.94276 11.4031 8.89176 11.8085 8.93304 12.2101L8.91915 12.1966C8.96005 12.6689 8.89439 13.1443 8.72688 13.5895C8.5593 14.0346 8.29389 14.4389 7.94908 14.7741C7.60425 15.1093 7.18835 15.3673 6.73039 15.5302C6.27242 15.693 5.78342 15.7569 5.29749 15.7171L5.31138 15.7306C4.73003 15.6775 4.14599 15.8001 3.63892 16.0815C3.13186 16.363 2.72644 16.7896 2.478 17.3033C2.22954 17.817 2.15013 18.3926 2.25061 18.9518C2.35109 19.5109 2.62657 20.0263 3.03945 20.4276C3.45234 20.829 3.98253 21.0968 4.55773 21.1944C5.13293 21.2921 5.72512 21.2149 6.25353 20.9734C6.78193 20.7319 7.22085 20.3379 7.51038 19.8449C7.79994 19.352 7.92601 18.7843 7.87139 18.2191L7.88605 18.2326C7.845 17.7602 7.91058 17.2849 8.07809 16.8396C8.24551 16.3944 8.511 15.99 8.85581 15.6548C9.20069 15.3196 9.61664 15.0615 10.0746 14.8988C10.5327 14.7359 11.0217 14.6722 11.5077 14.7121ZM17.1996 10.7633C16.9071 11.0493 16.6832 11.3944 16.5437 11.7741C16.4042 12.1538 16.3526 12.5587 16.3925 12.9601L16.3786 12.9466C16.4197 13.419 16.3541 13.8944 16.1866 14.3396C16.0191 14.7849 15.7537 15.1892 15.4089 15.5244C15.064 15.8596 14.648 16.1177 14.19 16.2804C13.732 16.4433 13.2429 16.507 12.757 16.4671L12.7708 16.4806C12.1896 16.4281 11.6057 16.551 11.0989 16.8328C10.5921 17.1145 10.1871 17.5414 9.93902 18.0551C9.69097 18.5689 9.61188 19.1444 9.71265 19.7035C9.81349 20.2625 10.0892 20.7777 10.5022 21.1788C10.9152 21.5799 11.4454 21.8474 12.0205 21.9448C12.5957 22.0423 13.1877 21.9649 13.716 21.7234C14.2443 21.4817 14.683 21.0877 14.9724 20.5947C15.2618 20.1018 15.3878 19.5342 15.3332 18.9692L15.3478 18.9827C15.3068 18.5103 15.3723 18.0349 15.5398 17.5896C15.7073 17.1444 15.9728 16.7401 16.3176 16.4048C16.6625 16.0696 17.0784 15.8115 17.5364 15.6488C17.9945 15.486 18.4835 15.4222 18.9695 15.4621L18.9548 15.4486C19.4296 15.4901 19.9076 15.4144 20.3444 15.2286C20.7811 15.0427 21.1625 14.7527 21.4533 14.3854C21.744 14.0181 21.9347 13.5854 22.0075 13.1274C22.0805 12.6694 22.0332 12.2009 21.8703 11.7653C21.7073 11.3298 21.4339 10.9413 21.0754 10.6358C20.7168 10.3303 20.2848 10.1178 19.8192 10.0179C19.3536 9.91795 18.8697 9.93385 18.4121 10.0641C17.9546 10.1945 17.5383 10.4349 17.2019 10.7633H17.1996Z" fill="currentColor"/>
                    </svg>
                    <span class="font-medium text-xl tracking-tight">Jenny</span>
                </div>
                <div class="text-sm text-gray-500 mb-4">Subscribe to our newsletter</div>
                <div class="flex gap-2 border-b border-gray-200 pb-2 mb-8">
                    <input type="email" placeholder="Email address" class="w-full outline-none text-sm" />
                    <button class="text-gray-400 hover:text-black">→</button>
                </div>
                <div class="text-xs text-gray-400">© Jenny 2025</div>
            </div>

            <div class="grid grid-cols-2 md:grid-cols-3 gap-8 col-span-1 md:col-span-3">
                <div>
                    <h4 class="text-xs font-bold text-gray-400 uppercase tracking-wider mb-6">Product</h4>
                    <ul class="space-y-3 text-sm text-gray-600">
                        <li><a href="#" class="hover:text-black">How it works</a></li>
                        <li><a href="#" class="hover:text-black">Research</a></li>
                        <li><a href="#" class="hover:text-black">Pricing</a></li>
                        <li><a href="#" class="hover:text-black">FAQ</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-xs font-bold text-gray-400 uppercase tracking-wider mb-6">Resources</h4>
                    <ul class="space-y-3 text-sm text-gray-600">
                        <li><a href="#" class="hover:text-black">RTI Guide</a></li>
                        <li><a href="#" class="hover:text-black">Teacher stories</a></li>
                        <li><a href="#" class="hover:text-black">Documentation</a></li>
                        <li><a href="#" class="hover:text-black">Support</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-xs font-bold text-gray-400 uppercase tracking-wider mb-6">Company</h4>
                    <ul class="space-y-3 text-sm text-gray-600">
                        <li><a href="#" class="hover:text-black">About</a></li>
                        <li><a href="#" class="hover:text-black">Contact</a></li>
                        <li><a href="#" class="hover:text-black">Privacy</a></li>
                        <li><a href="#" class="hover:text-black">Terms</a></li>
                    </ul>
                </div>
            </div>
        </div>
    </footer>

</div>

