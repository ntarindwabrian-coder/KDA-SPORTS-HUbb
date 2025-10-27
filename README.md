<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KDA Achievers</title>
    <!-- Load Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Configure Tailwind to use Inter font and custom colors (simulated KDA colors) -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    },
                    colors: {
                        kda_primary: '#1D4ED8', // Dark Bluem;i
                        kda_accent: '#FBBF24',  // Gold/Amber
                    }
                }
            }
        }
    </script>
    <!-- Load Lucide icons for clean UI elements -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <style>
        /* Custom scrollbar for better aesthetics */
        .achievement-scroll::-webkit-scrollbar {
            height: 6px;
        }
        .achievement-scroll::-webkit-scrollbar-thumb {
            background-color: #9CA3AF; /* gray-400 */
            border-radius: 3px;
        }
        .achievement-scroll::-webkit-scrollbar-track {
            background-color: #E5E7EB; /* gray-200 */
        }
    </style>
</head>
<body class="bg-gray-50 font-sans antialiased">

    <!-- Header & Navigation -->
    <header class="sticky top-0 bg-white shadow-md z-30">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8 py-3 flex justify-between items-center">
            <!-- Logo/School Name -->
            <div class="flex items-center space-x-2">
                <span class="text-3xl font-extrabold text-kda_primary">KDA</span>
                <span class="hidden sm:inline text-xl font-semibold text-gray-700">KDA Achievers</span>
            </div>

            <!-- Desktop Menu -->
            <nav class="hidden md:flex space-x-6 text-lg font-medium">
                <a href="#achievements" class="text-kda_primary hover:text-kda_accent transition duration-150">Achievements</a>
                <a href="#gallery" class="text-gray-600 hover:text-kda_primary transition duration-150">Photos</a>
                <a href="#news" class="text-gray-600 hover:text-kda_primary transition duration-150">Latest Announcements</a>
                <button class="text-gray-600 hover:text-kda_primary transition duration-150 flex items-center" onclick="alert('Admin login feature is under development!')">
                    Admin Panel
                    <i data-lucide="shield" class="w-5 h-5 ml-1"></i>
                </button>
            </nav>

            <!-- Mobile Menu Button -->
            <button id="mobile-menu-button" class="md:hidden p-2 text-gray-700 hover:bg-gray-100 rounded-lg">
                <i data-lucide="menu" class="w-6 h-6"></i>
            </button>
        </div>

        <!-- Mobile Menu Drawer (Hidden by default) -->
        <div id="mobile-menu" class="hidden md:hidden bg-white shadow-lg border-t border-gray-100 pb-2">
            <nav class="flex flex-col space-y-2 p-4 text-center">
                <a href="#achievements" class="block py-2 text-lg text-kda_primary font-medium hover:bg-gray-50 rounded-lg">Achievements</a>
                <a href="#gallery" class="block py-2 text-lg text-gray-600 hover:bg-gray-50 rounded-lg">Gallery</a>
                <a href="#news" class="block py-2 text-lg text-gray-600 hover:bg-gray-50 rounded-lg">News & Updates</a>
                <button class="py-2 text-lg text-gray-600 hover:bg-gray-50 rounded-lg flex items-center justify-center" onclick="alert('Admin login feature is under development!')">
                    Admin Panel
                    <i data-lucide="shield" class="w-5 h-5 ml-1"></i>
                </button>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="bg-kda_primary text-white py-16 px-4 sm:px-6 lg:px-8 shadow-xl">
        <div class="container mx-auto text-center max-w-4xl">
            <h1 class="text-4xl sm:text-5xl font-extrabold mb-3 leading-tight">
                
                Honouring Excellence at KDA
            </h1>
            <p class="text-xl sm:text-2xl opacity-90 mb-6">
                Recognizing the hard work, talent, and leadership of our outstanding students.
            </p>
            <a href="#achievements" class="inline-flex items-center bg-kda_accent text-kda_primary font-bold py-3 px-8 rounded-full shadow-lg hover:shadow-xl transition duration-300 transform hover:scale-105">
                View All Achievements
                <i data-lucide="arrow-right" class="w-5 h-5 ml-2"></i>
            </a>
        </div>
    </section>

    <main class="container mx-auto px-4 sm:px-6 lg:px-8 py-12">

        <!-- Search and Filter UI -->
        <section class="mb-10 p-6 bg-white rounded-xl shadow-lg border border-gray-100">
            <h2 class="text-2xl font-bold text-gray-800 mb-4 flex items-center">
                <i data-lucide="search" class="w-6 h-6 mr-2 text-kda_primary"></i>
                Search & Filter Achievements
            </h2>
            <div class="grid grid-cols-1 md:grid-cols-4 gap-4">
                <input type="text" placeholder="Search by name, award, or keyword..."
                       class="col-span-1 md:col-span-2 p-3 border border-gray-300 rounded-lg focus:ring-kda_primary focus:border-kda_primary">
                
                <select class="p-3 border border-gray-300 rounded-lg focus:ring-kda_primary focus:border-kda_primary">
                    <option>Filter by Category</option>
                    <option>Academic</option>
                    <option>Sports</option>
                    <option>Arts & Culture</option>
                    <option>Leadership</option>
                </select>

                <select class="p-3 border border-gray-300 rounded-lg focus:ring-kda_primary focus:border-kda_primary">
                    <option>Filter by Year</option>
                    <option>2025</option>
                    <option>2024</option>
                    <option>2023</option>
                </select>
            </div>
            <button class="mt-4 w-full md:w-auto bg-kda_primary text-white py-3 px-6 rounded-lg font-semibold hover:bg-blue-700 transition duration-150">
                Apply Filters
            </button>
        </section>


        <!-- Achievement Page & Student Profiles Grid -->
        <section id="achievements" class="mb-16">
            <h2 class="text-3xl font-extrabold text-kda_primary mb-8 border-b-2 border-kda_accent pb-2">
                Successful individuals
            </h2>

            <!-- Achievement/Student Profile Grid -->
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6">

                <!-- Profile Card 1: Academic -->
                <div class="bg-white p-6 rounded-xl shadow-lg hover:shadow-xl transition duration-300 transform hover:translate-y-[-2px]">
                    <div class="flex flex-col items-center text-center">
                        <!-- Student Profile Image Placeholder: Replace the path/to/student/image.jpg with the actual image URL or file path. -->
                        <img class="w-24 h-24 rounded-full object-cover mb-4 ring-4 ring-kda_accent" 
                             src="image/539643143_17896418229276356_7829889917127372980_n.webp" 
                             alt="NGANJI ethan Profile Picture" onerror="this.src='https://placehold.co/100x100/1D4ED8/FFFFFF?text=N.E.'">
                        <h3 class="text-xl font-bold text-gray-900">NGANJI Ethan</h3>
                        <p class="text-kda_primary font-semibold mb-3">Grade 11</p>
                        <p class="text-sm text-gray-700 italic mb-3">Exhibited exceptional analytical thinking and commitment while addressing advanced, real-world problems in the final stage.</p>
                    </div>
                    <div class="mt-3 pt-3 border-t border-gray-100">
                        <p class="text-sm font-medium text-gray-500">Achievement</p>
                        <p class="text-lg font-semibold text-gray-800">National Math Olympiad Winner</p>
                        <span class="inline-block mt-2 px-3 py-1 text-xs font-semibold rounded-full bg-blue-100 text-blue-800">Academic</span>
                    </div>
                    <button class="mt-4 w-full text-kda_primary hover:underline font-medium text-sm">
                        View Full Profile (Mock)
                    </button>
                </div>

                <!-- Profile Card 2: Sports -->
                <div class="bg-white p-6 rounded-xl shadow-lg hover:shadow-xl transition duration-300 transform hover:translate-y-[-2px]">
                    <div class="flex flex-col items-center text-center">
                        <!-- Student Profile Image Placeholder: Replace the path/to/student/image.jpg with the actual image URL or file path. -->
                        <img class="w-24 h-24 rounded-full object-cover mb-4 ring-4 ring-kda_accent" 
                             src="image/GID.png" 
                             alt="NTWALI GidloxProfile Picture" onerror="this.src='https://placehold.co/100x100/1D4ED8/FFFFFF?text=N.G.'">
                        <h3 class="text-xl font-bold text-gray-900">NTWALI Gidlox</h3>
                        <p class="text-kda_primary font-semibold mb-3">Grade 11</p>
                        <p class="text-sm text-gray-700 italic mb-3">Broke the school record with months of rigorous training, securing first place in a tight state final.</p>
                    </div>
                    <div class="mt-3 pt-3 border-t border-gray-100">
                        <p class="text-sm font-medium text-gray-500">Achievement</p>
                        <p class="text-lg font-semibold text-gray-800">State Track & Field Champion (100m)</p>
                        <span class="inline-block mt-2 px-3 py-1 text-xs font-semibold rounded-full bg-green-100 text-green-800">Sports</span>
                    </div>
                    <button class="mt-4 w-full text-kda_primary hover:underline font-medium text-sm">
                        View Full Profile (Mock)
                    </button>
                </div>

                <!-- Profile Card 3: Arts -->
                <div class="bg-white p-6 rounded-xl shadow-lg hover:shadow-xl transition duration-300 transform hover:translate-y-[-2px]">
                    <div class="flex flex-col items-center text-center">
                        <!-- Student Profile Image Placeholder: Replace the path/to/student/image.jpg with the actual image URL or file path. -->
                        <img class="w-24 h-24 rounded-full object-cover mb-4 ring-4 ring-kda_accent" 
                             src="image/mirreal2.png" 
                             alt="MIR Junior Profile Picture" onerror="this.src='https://placehold.co/100x100/1D4ED8/FFFFFF?text=MIR.'">
                        <h3 class="text-xl font-bold text-gray-900">MIR Junior</h3>
                        <p class="text-kda_primary font-semibold mb-3">Grade 11</p>
                        <p class="text-sm text-gray-700 italic mb-3">:Mir Junior, an award-winning upcoming artist from KDA, is recognised for his talent with songs like “Freestyle” and “SinaloA.”**

If you want, I can make an **even snappier one-line version** suitable for a website card.
.</p>
                    </div>
                    <div class="mt-3 pt-3 border-t border-gray-100">
                        <p class="text-sm font-medium text-gray-500">Achievement</p>
                        <p class="text-lg font-semibold text-gray-800">Regional IT Showcase Best in Class</p>
                        <span class="inline-block mt-2 px-3 py-1 text-xs font-semibold rounded-full bg-purple-100 text-purple-800">Arts & Culture</span>
                    </div>
                    <button class="mt-4 w-full text-kda_primary hover:underline font-medium text-sm">
                        View Full Profile (Mock)
                    </button>
                </div>

                <!-- Profile Card 4: Leadership -->
                <div class="bg-white p-6 rounded-xl shadow-lg hover:shadow-xl transition duration-300 transform hover:translate-y-[-2px]">
                    <div class="flex flex-col items-center text-center">
                        <!-- Student Profile Image Placeholder: Replace the path/to/student/image.jpg with the actual image URL or file path. -->
                        <img class="w-24 h-24 rounded-full object-cover mb-4 ring-4 ring-kda_accent" 
                             src="image/KAY G.png" 
                             alt="NTARINDWA Brian Profile Picture" onerror="this.src='https://placehold.co/100x100/1D4ED8/FFFFFF?text=NB.'">
                        <h3 class="text-xl font-bold text-gray-900">NTARINDWA Brian</h3>
                        <p class="text-kda_primary font-semibold mb-3">Grade 11</p>
                        <p class="text-sm text-gray-700 italic mb-3">Led a successful team focused on playing against other strong football teams and was the team captain</p>
                    </div>
                    <div class="mt-3 pt-3 border-t border-gray-100">
                        <p class="text-sm font-medium text-gray-500">Achievement</p>
                        <p class="text-lg font-semibold text-gray-800">Honoured as the best team captain in the school’s history.</p>
                        <span class="inline-block mt-2 px-3 py-1 text-xs font-semibold rounded-full bg-red-100 text-red-800">Leadership</span>
                    </div>
                    <button class="mt-4 w-full text-kda_primary hover:underline font-medium text-sm">
                        View Full Profile (Mock)
                    </button>
                </div>
            </div>
        </section>

        <!-- Photo and Video Gallery -->
        <section id="gallery" class="mb-16">
            <h2 class="text-3xl font-extrabold text-kda_primary mb-8 border-b-2 border-kda_accent pb-2 flex items-center">
                <i data-lucide="image" class="w-7 h-7 mr-2"></i>
                Photo & Video Gallery
            </h2>
            <p class="text-gray-600 mb-6">A visual celebration of KDA students in action across all areas of school life.</p>
            
            <!-- Horizontal Scroll Gallery (Updated with visible captions) -->
            <div class="flex overflow-x-auto space-x-4 pb-4 achievement-scroll">
                
                <!-- Gallery Item 1: Sports Day -->
                <div class="flex-shrink-0 w-64 bg-white rounded-xl shadow-lg group hover:shadow-xl transition duration-300">
                    <!-- Image/Video Area -->
                    <div class="w-full h-40 bg-gray-200 relative overflow-hidden rounded-t-xl">
                        <img class="w-full h-full object-cover transition duration-300 group-hover:scale-105" 
                             src="image/KDA SPORTS.png" 
                             alt="KDA Sports Day" onerror="this.src='https://placehold.co/256x160/1D4ED8/FFFFFF?text=Sports+Day'">
                    </div>
                    <!-- Caption Area -->
                    <div class="p-3">
                        <h4 class="font-bold text-gray-900 truncate">Sports Day 2024</h4>
                        <p class="text-sm text-gray-600 mt-0.5">The girls’ volleyball team triumphed with skill, teamwork, and determination, proudly winning the match and bringing glory to their school.</p>
                    </div>
                </div>

                <!-- Gallery Item 2: Science Fair -->
                <div class="flex-shrink-0 w-64 bg-white rounded-xl shadow-lg group hover:shadow-xl transition duration-300">
                    <!-- Image/Video Area -->
                    <div class="w-full h-40 bg-gray-200 relative overflow-hidden rounded-t-xl">
                        <img class="w-full h-full object-cover transition duration-300 group-hover:scale-105" 
                             src="image/SCIENCE FAIR.png" 
                             alt="Winning Science Project" onerror="this.src='https://placehold.co/256x160/FBBF24/1D4ED8?text=Science+Fair'">
                    </div>
                    <!-- Caption Area -->
                    <div class="p-3">
                        <h4 class="font-bold text-gray-900 truncate">The Best Science Fair Project</h4>
                        <p class="text-sm text-gray-600 mt-0.5">The school’s best science fair project showcased an innovative renewable energy model, proving how simple technology can power a sustainable future.</p>
                    </div>
                </div>

                <!-- Gallery Item 3: Graduation Party -->
                <div  class="flex-shrink-0 w-64 bg-white rounded-xl shadow-lg group hover:shadow-xl transition duration-300">
    <div class="w-full h-40 bg-gray-200 relative overflow-hidden rounded-t-xl">
        <video controls 
               poster="path/to/a/preview/image.jpg"
               class="w-full h-full object-cover transition duration-300 group-hover:scale-105 rounded-t-xl">
            <source src="videos/KING DAVID ACADEMY GRADUATION CEREMONY, Class of 2024 - YouTube - Google Chrome 2025-10-14 12-19-56.mp4" 
                    type="video/mp4">
            
            <track kind="captions" 
                   src="videos/graduation_captions_en.vtt" 
                   srclang="en" 
                   label="English Captions" 
                   default>
            
            Your browser does not support the video tag.
        </video>
        
        <div class="absolute inset-0 bg-black bg-opacity-20 flex items-center justify-center pointer-events-none">
            <i data-lucide="play-circle" class="w-10 h-10 text-white/90 group-hover:text-white transition duration-300"></i>
        </div>
    </div>
    <div class="p-3">
        <h4 class="font-bold text-gray-900 truncate">Graduation Party</h4>
        <p class="text-sm text-gray-600 mt-0.5">The King David Academy graduation party was a joyful celebration of achievement, filled with music, smiles, and pride as students marked a new beginning..</p>
    </div>
</div>

                 <!-- Gallery Item 4: Volunteer Day -->
                 <div class="flex-shrink-0 w-64 bg-white rounded-xl shadow-lg group hover:shadow-xl transition duration-300">
                    <!-- Image/Video Area -->
                    <div class="w-full h-40 bg-gray-200 relative overflow-hidden rounded-t-xl">
                        <img class="w-full h-full object-cover transition duration-300 group-hover:scale-105" 
                             src="image/COMMUNITY SERVICE.png" 
                             alt="Community Service Day" onerror="this.src='https://placehold.co/256x160/FBBF24/1D4ED8?text=Volunteer+Day'">
                    </div>
                    <!-- Caption Area -->
                    <div class="p-3">
                        <h4 class="font-bold text-gray-900 truncate">Community Service</h4>
                        <p class="text-sm text-gray-600 mt-0.5">Students showed teamwork and care by cleaning up the local park during the annual Community Service Day, making the environment cleaner and more beautiful.</p>
                    </div>
                </div>

                 <!-- Gallery Item 5: Debate Team -->
                 <div class="flex-shrink-0 w-64 bg-white rounded-xl shadow-lg group hover:shadow-xl transition duration-300">
                    <!-- Image/Video Area -->
                    <div class="w-full h-40 bg-gray-200 relative overflow-hidden rounded-t-xl">
                        <img class="w-full h-full object-cover transition duration-300 group-hover:scale-105" 
                             src="image/DEBATE.png" 
                             alt="Debate Team Victory" onerror="this.src='https://placehold.co/256x160/1D4ED8/FFFFFF?text=Debate+Team'">
                    </div>
                    <!-- Caption Area -->
                    <div class="p-3">
                        <h4 class="font-bold text-gray-900 truncate">Debate Team Victory</h4>
                        <p class="text-sm text-gray-600 mt-0.5">The debate team celebrated their regional championship victory with pride after delivering a powerful and convincing final performance.</p>
                    </div>
                </div>
                
            </div>
            <div class="mt-4 text-center">
                <button class="text-kda_primary font-semibold hover:underline flex items-center mx-auto">
                    Load More Photos
                    <i data-lucide="chevrons-down" class="w-4 h-4 ml-1"></i>
                </button>
            </div>
        </section>

        <!-- News and Updates -->
       <section id="latest-news" class="py-12 bg-gray-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <h2 class="text-3xl font-extrabold text-gray-900 mb-8 border-b-2 border-indigo-600 pb-2">Latest News & Announcements 📰</h2>
        
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            
            <article class="bg-white rounded-xl shadow-lg hover:shadow-xl transition duration-300 overflow-hidden border border-gray-200">
                <a href="news-detail-1.html" class="block">
                    <div class="h-48 w-full bg-indigo-100 overflow-hidden">
                        <img class="w-full h-full object-cover transition duration-300 hover:scale-105" 
                             src="image/PK.png" 
                             alt="New Principal Introduction">
                    </div>
                    <div class="p-5">
                        <p class="text-sm font-semibold text-indigo-600 uppercase mb-1">Prefect Council</p>
                        <h3 class="text-xl font-bold text-gray-900 mb-2 hover:text-indigo-700 transition duration-150">
                            Leadership mastery recognition
                        </h3>
                        <p class="text-gray-600 text-base line-clamp-3">
                           Crowning leadership excellence.
                        </p>
                        <p class="mt-4 text-xs text-gray-500">
                            **Date:** October 14, 2025
                        </p>
                    </div>
                </a>
            </article>
            <article class="bg-white rounded-xl shadow-lg hover:shadow-xl transition duration-300 overflow-hidden border border-gray-200">
                <a href="news-detail-2.html" class="block">
                    <div class="h-48 w-full bg-green-100 overflow-hidden">
                        <img class="w-full h-full object-cover transition duration-300 hover:scale-105" 
                             src="image/Screenshot 2025-10-16 103009.png" 
                             alt="Annual School Gala">
                    </div>
                    <div class="p-5">
                        <p class="text-sm font-semibold text-green-600 uppercase mb-1">Events</p>
                        <h3 class="text-xl font-bold text-gray-900 mb-2 hover:text-green-700 transition duration-150">
                           “Met Gala 2025: Celebrating the Night’s Best Look”
                        </h3>
                        <p class="text-gray-600 text-base line-clamp-3">
                           The night’s ultimate style icon.
                        </p>
                        <p class="mt-4 text-xs text-gray-500">
                            **Date:** October 10, 2025
                        </p>
                    </div>
                </a>
            </article>
            <article class="bg-white rounded-xl shadow-lg hover:shadow-xl transition duration-300 overflow-hidden border border-gray-200">
                <a href="news-detail-3.html" class="block">
                    <div class="h-48 w-full bg-yellow-100 overflow-hidden">
                        <img class="w-full h-full object-cover transition duration-300 hover:scale-105" 
                             src="image/kax.png" 
                             alt="Academic perfomance">
                        </div>
                    <div class="p-5">
                        <p class="text-sm font-semibold text-yellow-600 uppercase mb-1">Academics</p>
                        <h3 class="text-xl font-bold text-gray-900 mb-2 hover:text-yellow-700 transition duration-150">
                            Students Win National Science Bowl
                        </h3>
                        <p class="text-gray-600 text-base line-clamp-3">
                            A huge congratulations to our team of five 10th-grade students who took first place in the highly competitive National Science Bowl competition...
                        </p>
                        <p class="mt-4 text-xs text-gray-500">
                            **Date:** October 5, 2025
                        </p>
                    </div>
                </a>
            </article>
            </div>
        
        <div class="mt-10 text-center">
            <a href="news-archive.html" class="inline-flex items-center px-6 py-3 border border-transparent text-base font-medium rounded-md shadow-sm text-white bg-indigo-600 hover:bg-indigo-700 transition duration-300">
                View All News
            </a>
        </div>
        
    </div>
</section>

    </main>

    <!-- Footer -->
    <footer class="bg-gray-800 text-white py-10 px-4 sm:px-6 lg:px-8">
        <div class="container mx-auto text-center">
            <div class="text-2xl font-extrabold mb-3 text-kda_accent">KDA Achievement Hub</div>
            <p class="text-sm text-gray-400">
                A project dedicated to recognizing and promoting student excellence.
            </p>
            <div class="mt-6 flex justify-center space-x-6">
                <a href="#achievements" class="text-gray-300 hover:text-kda_accent transition">Achievements</a>
                <a href="#gallery" class="text-gray-300 hover:text-kda_accent transition">Gallery</a>
                <button onclick="alert('Contact details (e.g., email, phone) would go here.')" class="text-gray-300 hover:text-kda_accent transition">Contact</button>
            </div>
            <p class="mt-8 text-xs text-gray-500">
                &copy; 2025 KDA School. All rights reserved.
            </p>
        </div>
    </footer>

    <!-- JavaScript for Mobile Menu and Icon rendering -->
    <script>
        // Lucide icons are injected after the DOM loads
        document.addEventListener('DOMContentLoaded', () => {
            lucide.createIcons();
        });

        // Mobile menu toggle logic
        const mobileMenuButton = document.getElementById('mobile-menu-button');
        const mobileMenu = document.getElementById('mobile-menu');

        mobileMenuButton.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
            // Change icon to close (X) when menu is open
            const iconElement = mobileMenuButton.querySelector('svg');
            if (mobileMenu.classList.contains('hidden')) {
                iconElement.setAttribute('data-lucide', 'menu');
            } else {
                iconElement.setAttribute('data-lucide', 'x');
            }
            // Re-render icons if needed
            lucide.createIcons();
        });

        // Close mobile menu when a link is clicked
        const mobileLinks = mobileMenu.querySelectorAll('a');
        mobileLinks.forEach(link => {
            link.addEventListener('click', () => {
                mobileMenu.classList.add('hidden');
                mobileMenuButton.querySelector('svg').setAttribute('data-lucide', 'menu');
                lucide.createIcons();
            });
        });

        /**
         * Simple custom alert function to replace window.alert
         * This is a mock function for demonstration; a real app would use a modal UI.
         */
        function alert(message) {
            console.log("ALERT:", message);
            // In a real application, replace this with a beautiful modal or toast notification
            const notification = document.createElement('div');
            notification.className = 'fixed bottom-5 right-5 bg-kda_primary text-white p-4 rounded-xl shadow-2xl transition-opacity duration-300 opacity-0 z-50 max-w-sm';
            notification.textContent = message;
            document.body.appendChild(notification);
            
            // Fade in
            setTimeout(() => notification.classList.remove('opacity-0'), 10);
            
            // Fade out and remove
            setTimeout(() => {
                notification.classList.add('opacity-0');
                setTimeout(() => notification.remove(), 300);
            }, 3000);
        }

    </script>
</body>
</html>
