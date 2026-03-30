<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="IT with A.Richie - Tech projects, blogs, insights, and community discussions">
    <title>IT with A.Richie</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&amp;family=Space+Grotesk:wght@500;600;700&display=swap');
        
        :root {
            --primary: #00d4ff;
        }
        
        * {
            transition-property: color, background-color, border-color, text-decoration-color, fill, stroke;
            transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
            transition-duration: 150ms;
        }
        
        .tailwind-ready {
            font-family: 'Inter', system_ui, sans-serif;
        }
        
        .logo-font {
            font-family: 'Space Grotesk', sans-serif;
        }

        .hero-bg {
            background: linear-gradient(90deg, #0a0a0a 0%, #1a1a2e 100%);
        }
        
        .blog-card {
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }
        
        .blog-card:hover {
            transform: translateY(-4px);
            box-shadow: 0 20px 25px -5px rgb(0 212 255 / 0.2);
        }
        
        .modal {
            animation: modalPop 0.3s ease-out;
        }
        
        @keyframes modalPop {
            0% { transform: scale(0.95); opacity: 0; }
            100% { transform: scale(1); opacity: 1; }
        }
        
        .comment-bubble {
            animation: commentIn 0.4s ease-out;
        }
    </style>
</head>
<body class="tailwind-ready bg-zinc-950 text-white">
    <!-- NAVBAR -->
    <nav class="bg-zinc-900 border-b border-zinc-800 sticky top-0 z-50">
        <div class="max-w-7xl mx-auto px-6 py-5 flex items-center justify-between">
            <!-- Logo -->
            <div class="flex items-center gap-3">
                <div class="w-10 h-10 bg-cyan-400 rounded-2xl flex items-center justify-center text-zinc-950 font-bold text-2xl shadow-inner">IT</div>
                <div>
                    <h1 class="logo-font text-3xl font-semibold tracking-tighter">IT with A.Richie</h1>
                    <p class="text-xs text-cyan-400 -mt-1 font-medium">TECH • PROJECTS • COMMUNITY</p>
                </div>
            </div>

            <!-- Desktop Menu -->
            <div class="hidden md:flex items-center gap-8 text-sm font-medium">
                <a href="#home" onclick="navigateToSection('home')" class="hover:text-cyan-400 flex items-center gap-1">
                    <i class="fas fa-home"></i> HOME
                </a>
                <a href="#projects" onclick="navigateToSection('projects')" class="hover:text-cyan-400 flex items-center gap-1">
                    <i class="fas fa-rocket"></i> PROJECTS
                </a>
                <a href="#blogs" onclick="navigateToSection('blogs')" class="hover:text-cyan-400 flex items-center gap-1">
                    <i class="fas fa-newspaper"></i> BLOGS
                </a>
                <a href="#community" onclick="navigateToSection('community')" class="hover:text-cyan-400 flex items-center gap-1">
                    <i class="fas fa-users"></i> COMMUNITY
                </a>
            </div>

            <div class="flex items-center gap-4">
                <!-- GitHub / Social -->
                <a href="https://github.com" target="_blank" class="text-zinc-400 hover:text-white flex items-center gap-1 text-sm">
                    <i class="fab fa-github text-xl"></i>
                </a>
                <a href="#" onclick="showContact()" class="bg-cyan-400 hover:bg-cyan-300 text-zinc-950 px-5 py-2.5 rounded-2xl font-semibold flex items-center gap-2 text-sm">
                    <i class="fas fa-envelope"></i>
                    <span>CONTACT A.RICHIE</span>
                </a>
                
                <!-- Mobile menu button -->
                <button onclick="toggleMobileMenu()" class="md:hidden text-2xl">
                    <i class="fas fa-bars" id="mobile-menu-icon"></i>
                </button>
            </div>
        </div>
        
        <!-- Mobile Menu -->
        <div id="mobile-menu" class="hidden md:hidden bg-zinc-900 border-t border-zinc-800 px-6 py-4">
            <a href="#home" onclick="navigateToSection('home');toggleMobileMenu()" class="block py-3 px-4 hover:bg-zinc-800 rounded-2xl flex items-center gap-3">
                <i class="fas fa-home w-5"></i> HOME
            </a>
            <a href="#projects" onclick="navigateToSection('projects');toggleMobileMenu()" class="block py-3 px-4 hover:bg-zinc-800 rounded-2xl flex items-center gap-3">
                <i class="fas fa-rocket w-5"></i> PROJECTS
            </a>
            <a href="#blogs" onclick="navigateToSection('blogs');toggleMobileMenu()" class="block py-3 px-4 hover:bg-zinc-800 rounded-2xl flex items-center gap-3">
                <i class="fas fa-newspaper w-5"></i> BLOGS
            </a>
            <a href="#community" onclick="navigateToSection('community');toggleMobileMenu()" class="block py-3 px-4 hover:bg-zinc-800 rounded-2xl flex items-center gap-3">
                <i class="fas fa-users w-5"></i> COMMUNITY
            </a>
        </div>
    </nav>

    <!-- HERO -->
    <section id="home" class="hero-bg min-h-screen flex items-center relative overflow-hidden">
        <div class="max-w-7xl mx-auto px-6 grid md:grid-cols-2 gap-12 items-center">
            <div class="space-y-8">
                <div class="inline-flex items-center gap-2 bg-zinc-800 text-cyan-400 text-sm font-medium px-6 py-3 rounded-3xl">
                    <i class="fas fa-fire"></i>
                    NEW: My latest project just dropped!
                </div>
                
                <h1 class="text-6xl md:text-7xl font-bold leading-none logo-font tracking-tighter">
                    IT with<br><span class="text-cyan-400">A.Richie</span>
                </h1>
                
                <p class="text-xl text-zinc-400 max-w-md">
                    Tech projects • Deep-dive blogs • Real conversations.<br>
                    Built in Accra, Ghana. Shared with the world.
                </p>
                
                <div class="flex flex-wrap gap-4">
                    <button onclick="navigateToSection('projects')" 
                            class="bg-cyan-400 hover:bg-cyan-300 text-zinc-950 font-semibold text-lg px-8 py-4 rounded-3xl flex items-center gap-3 shadow-2xl shadow-cyan-400/30">
                        <i class="fas fa-rocket"></i>
                        EXPLORE MY PROJECTS
                    </button>
                    <button onclick="navigateToSection('blogs')" 
                            class="border border-cyan-400 hover:bg-cyan-400 hover:text-zinc-950 font-semibold text-lg px-8 py-4 rounded-3xl flex items-center gap-3">
                        <i class="fas fa-book"></i>
                        READ LATEST BLOG
                    </button>
                </div>
                
                <div class="flex items-center gap-8 text-sm">
                    <div>
                        <span class="block text-cyan-400 font-mono">42</span>
                        PROJECTS SHIPPED
                    </div>
                    <div>
                        <span class="block text-cyan-400 font-mono">128</span>
                        BLOG POSTS
                    </div>
                    <div>
                        <span class="block text-cyan-400 font-mono">3.8K</span>
                        COMMUNITY MEMBERS
                    </div>
                </div>
            </div>
            
            <!-- Hero visual -->
            <div class="relative hidden md:block">
                <div class="absolute -inset-20 bg-gradient-to-br from-cyan-400/20 to-transparent rounded-[4rem] -rotate-6"></div>
                <div class="bg-zinc-900 border border-cyan-400/30 rounded-3xl p-8 shadow-2xl relative">
                    <div class="aspect-video bg-black rounded-2xl flex items-center justify-center overflow-hidden">
                        <div class="text-center">
                            <i class="fas fa-code text-cyan-400 text-8xl mb-4"></i>
                            <p class="text-cyan-400 font-mono text-sm">LIVE DEMO PROJECT</p>
                            <p class="text-zinc-400 mt-2">A.Richie’s AI-Powered Portfolio Builder</p>
                        </div>
                    </div>
                </div>
                <div class="absolute -bottom-6 -right-6 bg-zinc-800 rounded-2xl px-6 py-3 flex items-center gap-3 shadow-xl">
                    <div class="w-3 h-3 bg-green-400 rounded-full animate-pulse"></div>
                    <span class="font-medium">Currently online • 47 people reading this page</span>
                </div>
            </div>
        </div>
        
        <div class="absolute bottom-10 left-1/2 flex flex-col items-center gap-2 text-zinc-400 text-sm">
            SCROLL FOR PROJECTS
            <i class="fas fa-chevron-down animate-bounce"></i>
        </div>
    </section>

    <!-- PROJECTS SECTION -->
    <section id="projects" class="max-w-7xl mx-auto px-6 py-24">
        <div class="flex items-end justify-between mb-12">
            <div>
                <span class="text-cyan-400 font-medium text-sm tracking-widest">MY WORK</span>
                <h2 class="text-5xl font-bold logo-font tracking-tighter">Featured Projects</h2>
            </div>
            <a href="#" onclick="alert('You can add your real project links here in the code!')" 
               class="text-cyan-400 flex items-center gap-2 hover:gap-3">
                VIEW ALL PROJECTS <i class="fas fa-arrow-right"></i>
            </a>
        </div>
        
        <div class="grid md:grid-cols-3 gap-8" id="projects-grid">
            <!-- Populated by JavaScript -->
        </div>
    </section>

    <!-- BLOGS SECTION -->
    <section id="blogs" class="bg-zinc-900 py-24">
        <div class="max-w-7xl mx-auto px-6">
            <div class="flex items-end justify-between mb-12">
                <div>
                    <span class="text-cyan-400 font-medium text-sm tracking-widest">LATEST INSIGHTS</span>
                    <h2 class="text-5xl font-bold logo-font tracking-tighter">Blogs &amp; Articles</h2>
                </div>
                <button onclick="openNewBlogModal()" 
                        class="bg-zinc-800 hover:bg-zinc-700 text-white px-6 py-3 rounded-3xl flex items-center gap-2 text-sm font-semibold">
                    <i class="fas fa-plus"></i> WRITE NEW BLOG (ADMIN)
                </button>
            </div>
            
            <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8" id="blogs-grid">
                <!-- Populated by JavaScript -->
            </div>
        </div>
    </section>

    <!-- COMMUNITY / INTERACTION SECTION -->
    <section id="community" class="max-w-7xl mx-auto px-6 py-24">
        <h2 class="text-5xl font-bold logo-font tracking-tighter text-center mb-4">Join the Conversation</h2>
        <p class="text-zinc-400 text-center max-w-md mx-auto mb-16">
            Read blogs, leave comments, discuss projects, and connect with other IT enthusiasts.
        </p>
        
        <div class="bg-zinc-900 rounded-3xl p-8 max-w-2xl mx-auto">
            <div class="flex justify-center gap-8 mb-8">
                <div onclick="switchTab(0)" id="tab-0" class="community-tab active flex-1 text-center py-4 rounded-2xl cursor-pointer font-medium">Recent Comments</div>
                <div onclick="switchTab(1)" id="tab-1" class="community-tab flex-1 text-center py-4 rounded-2xl cursor-pointer font-medium">Live Discussions</div>
            </div>
            
            <!-- Comments feed (demo) -->
            <div id="community-feed">
                <!-- Populated by JS -->
            </div>
        </div>
    </section>

    <!-- BLOG MODAL -->
    <div onclick="if(event.target.id === 'blog-modal')closeBlogModal()" 
         id="blog-modal" 
         class="hidden fixed inset-0 bg-black/80 z-[9999] flex items-center justify-center">
        
        <div onclick="event.stopImmediatePropagation()" 
             class="modal bg-zinc-900 rounded-3xl max-w-4xl w-full mx-4 max-h-[90vh] overflow-hidden flex flex-col">
            
            <div class="p-6 border-b flex items-center justify-between">
                <div id="modal-blog-title" class="text-3xl font-bold"></div>
                <button onclick="closeBlogModal()" class="text-3xl text-zinc-400 hover:text-white">×</button>
            </div>
            
            <div class="flex-1 overflow-auto p-8" id="modal-blog-content">
                <!-- Content injected by JS -->
            </div>
            
            <!-- Comments inside modal -->
            <div class="border-t p-8">
                <h3 class="font-semibold mb-6 flex items-center gap-2"><i class="fas fa-comments"></i> Comments • Be respectful</h3>
                
                <div id="modal-comments" class="space-y-6 mb-8 max-h-64 overflow-auto">
                    <!-- JS injected -->
                </div>
                
                <!-- Add comment form -->
                <div class="flex gap-3">
                    <input id="comment-input" 
                           type="text" 
                           placeholder="Write your thoughts here..." 
                           class="flex-1 bg-zinc-800 border border-zinc-700 rounded-3xl px-6 py-4 outline-none focus:border-cyan-400">
                    <button onclick="submitComment()" 
                            class="bg-cyan-400 text-zinc-950 px-8 rounded-3xl font-semibold">POST</button>
                </div>
                <p class="text-xs text-zinc-400 mt-3">Comments are saved locally for this demo. For real hosting, we’ll connect Disqus or Firebase.</p>
            </div>
        </div>
    </div>

    <!-- NEW BLOG MODAL (for demo admin) -->
    <div onclick="if(event.target.id === 'new-blog-modal')closeNewBlogModal()" 
         id="new-blog-modal" 
         class="hidden fixed inset-0 bg-black/80 z-[9999] flex items-center justify-center">
        <div class="modal bg-zinc-900 rounded-3xl w-full max-w-lg mx-4 p-8">
            <h3 class="text-2xl font-bold mb-6">Create New Blog Post</h3>
            
            <input id="new-blog-title" type="text" placeholder="Blog title" 
                   class="w-full bg-zinc-800 border border-zinc-700 rounded-3xl px-6 py-4 mb-4 outline-none">
            
            <textarea id="new-blog-excerpt" placeholder="Short description..." 
                      class="w-full bg-zinc-800 border border-zinc-700 rounded-3xl px-6 py-4 mb-4 outline-none h-28"></textarea>
            
            <textarea id="new-blog-full" placeholder="Full blog content (Markdown supported in real version)" 
                      class="w-full bg-zinc-800 border border-zinc-700 rounded-3xl px-6 py-4 outline-none h-64"></textarea>
            
            <div class="flex gap-4 mt-8">
                <button onclick="closeNewBlogModal()" 
                        class="flex-1 py-4 text-zinc-400 font-medium">CANCEL</button>
                <button onclick="createNewBlog()" 
                        class="flex-1 py-4 bg-cyan-400 text-zinc-950 rounded-3xl font-semibold">PUBLISH TO SITE</button>
            </div>
        </div>
    </div>

    <!-- FOOTER -->
    <footer class="bg-black py-16">
        <div class="max-w-7xl mx-auto px-6 grid md:grid-cols-4 gap-10">
            <div>
                <div class="flex items-center gap-3 mb-6">
                    <div class="w-8 h-8 bg-cyan-400 rounded-2xl flex items-center justify-center text-zinc-950 text-xl">IT</div>
                    <span class="logo-font text-3xl">IT with A.Richie</span>
                </div>
                <p class="text-zinc-400 text-sm">Building the future of IT from Accra, Ghana.<br>One project, one blog, one conversation at a time.</p>
                
                <div class="mt-8 flex gap-5 text-2xl text-zinc-400">
                    <i onclick="window.open('https://twitter.com','_blank')" class="fab fa-x-twitter cursor-pointer hover:text-cyan-400"></i>
                    <i onclick="window.open('https://linkedin.com','_blank')" class="fab fa-linkedin cursor-pointer hover:text-cyan-400"></i>
                    <i onclick="window.open('https://github.com','_blank')" class="fab fa-github cursor-pointer hover:text-cyan-400"></i>
                </div>
            </div>
            
            <div>
                <div class="uppercase text-xs font-medium text-zinc-400 mb-4">Quick Links</div>
                <ul class="space-y-3 text-sm">
                    <li><a href="#projects" onclick="navigateToSection('projects')" class="hover:text-cyan-400">Projects</a></li>
                    <li><a href="#blogs" onclick="navigateToSection('blogs')" class="hover:text-cyan-400">All Blogs</a></li>
                    <li><a href="#" class="hover:text-cyan-400">My Resume</a></li>
                    <li><a href="#" class="hover:text-cyan-400">Contact</a></li>
                </ul>
            </div>
            
            <div>
                <div class="uppercase text-xs font-medium text-zinc-400 mb-4">For Developers</div>
                <p class="text-sm text-zinc-400">Want to collaborate on a project?<br>Or guest post on the blog?</p>
                <button onclick="showContact()" class="mt-6 text-cyan-400 underline">Send me a message →</button>
            </div>
            
            <div class="text-xs text-zinc-400">
                © 2026 IT with A.Richie. All rights reserved.<br>
                Built as a live interactive demo by Grok for you.<br><br>
                <span class="text-cyan-400">How to host this instantly:</span><br>
                1. Copy everything above into a file called <strong>index.html</strong><br>
                2. Go to <a href="https://github.com" target="_blank" class="underline">GitHub</a> → New repo → Upload file → Enable GitHub Pages<br>
                3. Your site will be live in 60 seconds at <strong>yourusername.github.io/it-with-arichie</strong>
            </div>
        </div>
    </footer>

    <script>
        // Tailwind script initialization
        function initializeTailwind() {
            tailwind.config = {
                content: [],
                theme: {
                    extend: {}
                }
            }
        }
        
        // Sample Projects
        const sampleProjects = [
            {
                title: "AI Resume Builder",
                desc: "An intelligent tool that generates ATS-friendly resumes using local LLMs. Built with Next.js + Python.",
                tech: "Next.js • Python • Grok API",
                link: "#",
                emoji: "📄"
            },
            {
                title: "Ghana Tech Job Board",
                desc: "Real-time platform connecting developers in Accra with local startups. Includes skill-matching algorithm.",
                tech: "React • Firebase • Tailwind",
                link: "#",
                emoji: "💼"
            },
            {
                title: "Smart Energy Dashboard",
                desc: "IoT dashboard for monitoring solar panel performance in Ghanaian homes.",
                tech: "Node.js • MQTT • Chart.js",
                link: "#",
                emoji: "☀️"
            }
        ]
        
        // Sample Blogs
        let blogs = [
            {
                id: 1,
                title: "Why Every Developer in Ghana Should Learn AI in 2026",
                excerpt: "The future is here. Here’s how I built my first AI project in 3 weeks using only free tools.",
                date: "March 28, 2026",
                readTime: "8 min",
                fullContent: `
                    <h2 class="text-2xl font-bold mb-6">The AI revolution is not coming — it’s already here.</h2>
                    <p class="mb-6">As a developer based in Accra, I decided to stop waiting for “the right time” and just build. In this post I share the exact stack I used (no expensive GPUs needed) and the lessons I learned building my first production AI tool.</p>
                    <div class="bg-zinc-800 rounded-2xl p-8 my-8">
                        <strong>Tools used:</strong><br>
                        • Grok API (free tier)<br>
                        • Next.js 15<br>
                        • Tailwind + shadcn/ui<br>
                        • Local vector database
                    </div>
                    <p>Result? 200+ people have already used the tool and it runs entirely in the browser.</p>
                `
            },
            {
                id: 2,
                title: "Building a Comment System Without a Backend (This Website!)",
                excerpt: "How I made this entire interactive site using only HTML, Tailwind &amp; JavaScript. Zero server cost.",
                date: "March 25, 2026",
                readTime: "5 min",
                fullContent: `
                    <p class="mb-6">Yes — this website you’re reading right now has working comments, blog posting, and project cards… all running 100% client-side.</p>
                    <p>LocalStorage + clever JS makes it feel real. When you’re ready for real users, I’ll show you how to plug in Firebase or Supabase in 10 minutes.</p>
                `
            },
            {
                id: 3,
                title: "How I Turned My Side Project Into a Community of 3,800+ Techies",
                excerpt: "The exact growth strategy that took me from 0 to 3.8K engaged followers in Ghana’s tech scene.",
                date: "March 20, 2026",
                readTime: "12 min",
                fullContent: `
                    <p>Consistency beats perfection. Sharing one blog every week + replying to every comment changed everything.</p>
                `
            }
        ]
        
        // Global comments storage (per blog)
        let commentsDB = {}
        
        // Render Projects
        function renderProjects() {
            const container = document.getElementById('projects-grid')
            container.innerHTML = sampleProjects.map(project => `
                <div class="bg-zinc-900 border border-zinc-800 rounded-3xl p-8 hover:border-cyan-400 group">
                    <div class="text-6xl mb-6">${project.emoji}</div>
                    <h3 class="text-2xl font-semibold mb-2">${project.title}</h3>
                    <p class="text-zinc-400 mb-6">${project.desc}</p>
                    <div class="flex justify-between items-center">
                        <span class="text-xs font-mono bg-zinc-800 px-4 py-2 rounded-2xl">${project.tech}</span>
                        <a onclick="viewProject('${project.title}')" class="flex items-center gap-2 text-cyan-400 text-sm font-medium group-hover:gap-3">
                            VIEW PROJECT 
                            <i class="fas fa-arrow-right"></i>
                        </a>
                    </div>
                </div>
            `).join('')
        }
        
        // Render Blogs
        function renderBlogs() {
            const container = document.getElementById('blogs-grid')
            container.innerHTML = blogs.map(blog => `
                <div onclick="openBlog(${blog.id})" class="blog-card bg-white/5 border border-white/10 rounded-3xl p-6 cursor-pointer hover:border-cyan-400">
                    <div class="flex justify-between text-xs text-zinc-400 mb-3">
                        <span>${blog.date}</span>
                        <span>${blog.readTime}</span>
                    </div>
                    <h3 class="text-xl font-semibold leading-tight mb-3">${blog.title}</h3>
                    <p class="text-zinc-400 line-clamp-3">${blog.excerpt}</p>
                    <div class="mt-8 flex items-center justify-between text-xs">
                        <span class="text-cyan-400">Read full post →</span>
                        <span class="text-zinc-400">${blog.comments || 0} comments</span>
                    </div>
                </div>
            `).join('')
        }
        
        // Open blog modal
        let currentBlogId = null
        
        function openBlog(id) {
            const blog = blogs.find(b => b.id === id)
            if (!blog) return
            
            currentBlogId = id
            
            document.getElementById('modal-blog-title').innerHTML = blog.title
            document.getElementById('modal-blog-content').innerHTML = blog.fullContent || `<p class="text-zinc-400">${blog.excerpt}</p>`
            
            // Render comments for this blog
            renderModalComments()
            
            document.getElementById('blog-modal').classList.remove('hidden')
            document.getElementById('blog-modal').classList.add('flex')
        }
        
        function closeBlogModal() {
            const modal = document.getElementById('blog-modal')
            modal.classList.add('hidden')
            modal.classList.remove('flex')
            currentBlogId = null
        }
        
        // Render comments in modal
        function renderModalComments() {
            const container = document.getElementById('modal-comments')
            if (!commentsDB[currentBlogId]) commentsDB[currentBlogId] = []
            
            container.innerHTML = commentsDB[currentBlogId].length ? 
                commentsDB[currentBlogId].map(c => `
                    <div class="comment-bubble flex gap-4">
                        <div class="w-9 h-9 bg-gradient-to-br from-cyan-400 to-blue-400 rounded-2xl flex-shrink-0 flex items-center justify-center text-sm font-bold">👤</div>
                        <div class="flex-1">
                            <div class="flex justify-between">
                                <span class="font-medium">${c.author || 'Anonymous Reader'}</span>
                                <span class="text-zinc-400 text-xs">${c.time}</span>
                            </div>
                            <p class="text-zinc-300">${c.text}</p>
                        </div>
                    </div>
                `).join('') : 
                `<p class="text-zinc-400 italic">No comments yet. Be the first!</p>`
        }
        
        // Submit comment
        function submitComment() {
            const input = document.getElementById('comment-input')
            const text = input.value.trim()
            
            if (!text || !currentBlogId) return
            
            if (!commentsDB[currentBlogId]) commentsDB[currentBlogId] = []
            
            commentsDB[currentBlogId].unshift({
                author: "You (demo)",
                text: text,
                time: "just now"
            })
            
            // Also increment blog comment count
            const blog = blogs.find(b => b.id === currentBlogId)
            if (blog) blog.comments = (blog.comments || 0) + 1
            
            input.value = ''
            renderModalComments()
            
            // Refresh main blogs list too
            renderBlogs()
            
            // Little success animation
            const btn = document.querySelector('button[onclick="submitComment()"]')
            btn.innerHTML = '✅ POSTED!'
            setTimeout(() => { btn.innerHTML = 'POST' }, 1500)
        }
        
        // Create new blog (demo)
        function openNewBlogModal() {
            document.getElementById('new-blog-modal').classList.remove('hidden')
            document.getElementById('new-blog-modal').classList.add('flex')
        }
        
        function closeNewBlogModal() {
            const modal = document.getElementById('new-blog-modal')
            modal.classList.add('hidden')
            modal.classList.remove('flex')
        }
        
        function createNewBlog() {
            const title = document.getElementById('new-blog-title').value.trim()
            const excerpt = document.getElementById('new-blog-excerpt').value.trim()
            const full = document.getElementById('new-blog-full').value.trim()
            
            if (!title) {
                alert("Title is required!")
                return
            }
            
            const newBlog = {
                id: Date.now(),
                title: title,
                excerpt: excerpt || "New post from A.Richie",
                date: "March 30, 2026",
                readTime: "3 min",
                fullContent: full || `<p class="text-zinc-400">Thank you for publishing! Edit this post in the code to make it real.</p>`,
                comments: 0
            }
            
            blogs.unshift(newBlog)
            renderBlogs()
            closeNewBlogModal()
            
            alert("✅ Blog published! Refresh the page to see it live.")
        }
        
        // View project alert
        function viewProject(title) {
            alert(`🚀 You clicked on "${title}"\n\nIn the real hosted version, this would open your actual project (GitHub, live demo, Figma, etc.).\n\nJust replace the sample data with your real links in the code!`)
        }
        
        // Community tabs
        function switchTab(n) {
            document.querySelectorAll('.community-tab').forEach(el => el.classList.remove('active', 'bg-zinc-800'))
            document.getElementById('tab-' + n).classList.add('active', 'bg-zinc-800')
            
            const feed = document.getElementById('community-feed')
            if (n === 0) {
                feed.innerHTML = `
                    <div class="space-y-6">
                        <div class="flex gap-4">
                            <span class="text-cyan-400">👏</span>
                            <div><strong>Maame</strong> just commented on your AI Resume post: “This is exactly what I needed!”</div>
                        </div>
                        <div class="flex gap-4">
                            <span class="text-cyan-400">🔥</span>
                            <div><strong>Kwame</strong> replied to your Ghana Tech Job Board project: “When can I contribute?”</div>
                        </div>
                    </div>
                `
            } else {
                feed.innerHTML = `
                    <div class="text-center py-12">
                        <i class="fas fa-users text-6xl text-cyan-400 mb-4"></i>
                        <p class="font-medium">Live discussion happening now in the comments of “Why Every Developer Should Learn AI”</p>
                        <p class="text-zinc-400 text-sm mt-4">Join the chat • 12 people online</p>
                    </div>
                `
            }
        }
        
        // Mobile menu
        function toggleMobileMenu() {
            const menu = document.getElementById('mobile-menu')
            const icon = document.getElementById('mobile-menu-icon')
            if (menu.classList.contains('hidden')) {
                menu.style.display = 'block'
                icon.classList.replace('fa-bars', 'fa-xmark')
            } else {
                menu.style.display = 'none'
                icon.classList.replace('fa-xmark', 'fa-bars')
            }
        }
        
        // Smooth navigation
        function navigateToSection(section) {
            document.getElementById(section).scrollIntoView({ behavior: 'smooth' })
        }
        
        // Contact modal
        function showContact() {
            alert("📧 Hey! I'm A.Richie.\n\nYou can reach me at: hello@itwitharichie.com\n\n(Or just edit this alert in the code to point to your real email or WhatsApp)")
        }
        
        // Initialize everything
        function initWebsite() {
            initializeTailwind()
            renderProjects()
            renderBlogs()
            // Seed some initial comments for first blog
            commentsDB[1] = [
                { author: "Kwame O.", text: "This changed how I think about AI in Africa 🔥", time: "2h ago" },
                { author: "Nana Yaa", text: "Thank you for the free tools list!", time: "1d ago" }
            ]
            console.log('%c✅ IT with A.Richie website ready! Copy this entire file and host it for free on GitHub Pages.', 'color:#00d4ff; font-size:13px')
        }
        
        // Start the magic
        window.onload = initWebsite
    </script>
</body>
</html>
