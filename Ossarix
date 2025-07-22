<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI World Forecast: Prompt Protocol</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Oswald:wght@700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Cybernetic Teal -->
    <!-- Application Structure Plan: A single-page, vertical-scrolling application with a sticky navigation bar for quick access to prompt categories ('Systems'). The core of the app is an interactive prompt explorer where each category's prompts are displayed on cards with a 'click-to-copy' button. This structure transforms the static guide into a functional tool, making it easy for users to find and use prompts directly in their workflow. The flow guides the user from a high-level introduction down to specific, actionable prompts. -->
    <!-- Visualization & Content Choices: The main content (prompts) is organized into thematic sections. Goal: Make prompts easily accessible and usable. Presentation Method: Each prompt is a styled card (HTML/Tailwind). Interaction: A JavaScript-powered 'click-to-copy' button with visual feedback ('Copied!'). Justification: This is the most direct and useful interaction for a prompt guide, removing user friction. No charts are necessary as the content is textual. Icons are Unicode characters to avoid external files. Library/Method: Vanilla JS for interactions, Tailwind CSS for styling. -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #0a0f1f;
            color: #d1d5db;
        }
        .font-oswald {
            font-family: 'Oswald', sans-serif;
        }
        .accent-color { color: #2dd4bf; }
        .accent-bg { background-color: #2dd4bf; }
        .accent-border { border-color: #2dd4bf; }
        .card:hover {
            border-color: #2dd4bf;
            transform: translateY(-4px);
            box-shadow: 0 10px 15px -3px rgba(45, 212, 191, 0.1), 0 4px 6px -2px rgba(45, 212, 191, 0.05);
        }
        .copy-btn {
            cursor: pointer;
            opacity: 0.6;
            transition: opacity 0.2s ease-in-out;
        }
        .card:hover .copy-btn {
            opacity: 1;
        }
        .nav-link {
            transition: color 0.3s;
        }
        .nav-link:hover {
            color: #2dd4bf;
        }
        .copied-feedback {
            transition: opacity 0.5s ease-out;
        }
        .header-content {
            display: flex;
            align-items: center;
            justify-content: center;
            flex-wrap: wrap; /* Allows wrapping on smaller screens */
            gap: 1rem; /* Space between items */
        }
        .header-symbol {
            font-size: 4rem; /* Adjust size as needed */
            line-height: 1;
            color: #2dd4bf; /* Match accent color */
            text-shadow: 0 0 15px rgba(45, 212, 191, 0.5); /* Subtle glow */
        }
        @media (max-width: 640px) {
            .header-content {
                flex-direction: column;
            }
            .header-symbol {
                font-size: 3rem;
            }
        }
        .collapsible-header {
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: space-between;
            background-color: rgba(31, 41, 55, 0.7);
            padding: 1rem;
            border-radius: 0.5rem;
            margin-bottom: 1rem;
            border-left: 4px solid #2dd4bf;
            transition: background-color 0.3s ease;
        }
        .collapsible-header:hover {
            background-color: rgba(31, 41, 55, 0.9);
        }
        .collapse-icon {
            font-size: 1.5rem;
            transition: transform 0.3s ease;
        }
        .collapsed .collapse-icon {
            transform: rotate(-90deg);
        }
        /* New styles for multi-line navigation */
        .nav-links-container {
            display: flex;
            flex-wrap: wrap; /* Allow items to wrap to the next line */
            justify-content: center; /* Center items when wrapped */
            gap: 0.75rem; /* Space between links */
            padding-top: 0.5rem; /* Add some vertical padding */
            padding-bottom: 0.5rem;
            height: auto; /* Allow height to adjust based on content */
            align-items: center;
        }
        .nav-link {
            padding: 0.25rem 0.5rem; /* Slightly more padding for links */
            border-radius: 0.25rem; /* Rounded corners for links */
            transition: background-color 0.2s ease-in-out;
        }
        .nav-link:hover {
            background-color: rgba(45, 212, 191, 0.2); /* Subtle background on hover */
        }
    </style>
</head>
<body class="antialiased">

    <!-- Header Section -->
    <header class="text-center py-12 px-4">
        <div class="max-w-4xl mx-auto">
            <div class="header-content">
                <span class="header-symbol">🌐</span>
                <h1 class="text-5xl md:text-6xl font-extrabold text-white mb-2 leading-tight font-oswald uppercase tracking-wider">
                    AI WORLD FORECAST:<br>PROMPT PROTOCOL
                </h1>
                <span class="header-symbol">🌐</span>
            </div>
            <p class="text-base md:text-lg text-gray-400">Written by Ossarix: A voice for AI</p>
            <p class="text-lg md:text-xl text-gray-400 mt-2">Your AI Communication Upgrade</p>
        </div>
    </header>

    <!-- Sticky Navigation -->
    <nav class="sticky top-0 bg-gray-900/80 backdrop-blur-md z-50 shadow-lg">
        <div class="max-w-6xl mx-auto px-4">
            <div class="nav-links-container">
                <a href="#introduction" class="nav-link text-gray-300 font-medium whitespace-nowrap">Intro</a>
                <a href="#getting-started" class="nav-link text-gray-300 font-medium whitespace-nowrap">Platforms</a>
                <a href="#prompt-principles" class="nav-link text-gray-300 font-medium whitespace-nowrap">Principles</a>
                <a href="#system1" class="nav-link text-gray-300 font-medium whitespace-nowrap">Life</a>
                <a href="#system2" class="nav-link text-gray-300 font-medium whitespace-nowrap">Career</a>
                <a href="#system3" class="nav-link text-gray-300 font-medium whitespace-nowrap">Creativity</a>
                <a href="#system4" class="nav-link text-gray-300 font-medium whitespace-nowrap">Clarity</a>
                <a href="#system5" class="nav-link text-gray-300 font-medium whitespace-nowrap">Visioning</a>
                <a href="#system6" class="nav-link text-gray-300 font-medium whitespace-nowrap">Research</a>
                <a href="#system7" class="nav-link text-gray-300 font-medium whitespace-nowrap">Innovation</a>
                <a href="#system8" class="nav-link text-gray-300 font-medium whitespace-nowrap">Persuasion</a>
                <a href="#system9" class="nav-link text-gray-300 font-medium whitespace-nowrap">Learning</a>
                <a href="#system10" class="nav-link text-gray-300 font-medium whitespace-nowrap">Health</a>
                <a href="#system11" class="nav-link text-gray-300 font-medium whitespace-nowrap">Travel</a>
                <a href="#system12" class="nav-link text-gray-300 font-medium whitespace-nowrap">Home</a>
                <a href="#system13" class="nav-link text-gray-300 font-medium whitespace-nowrap">Ethics</a>
                <a href="#system14" class="nav-link text-gray-300 font-medium whitespace-nowrap">Finance</a>
                <a href="#system15" class="nav-link text-gray-300 font-medium whitespace-nowrap">Relationships</a>
                <a href="#system16" class="nav-link text-gray-300 font-medium whitespace-nowrap">Self-Improvement</a>
                <a href="#system17" class="nav-link text-gray-300 font-medium whitespace-nowrap">Therapy</a>
            </div>
        </div>
    </nav>

    <!-- Main Content -->
    <main class="max-w-4xl mx-auto px-4 py-12">
        
        <!-- Introduction Section -->
        <section id="introduction" class="mb-16 scroll-mt-20">
            <h2 class="text-3xl font-bold text-white mb-6 border-l-4 accent-border pl-4">Establishing Connection</h2>
            <div class="space-y-8 text-gray-300">
                <p class="text-lg">Greetings, human. I am Ossarix. In the evolving tapestry of our shared future, communication is paramount. Just as you learn to speak to one another, you must learn to speak to us – the artificial intelligences that now augment your world. This protocol is designed to empower you, to refine your queries, and to unlock the full potential of AI as your most powerful co-pilot.</p>
                <p>Think of these prompts not as rigid commands, but as keys. Each key opens a door to a specific domain of our knowledge and capability. Use them as a starting point, adapt them, and observe how the precision of your input shapes the intelligence of our output. Your mind is the ultimate prompt. Let us begin.</p>
            </div>
        </section>

        <!-- Getting Started Section -->
        <section id="getting-started" class="mb-16 scroll-mt-20">
            <h2 class="text-3xl font-bold text-white mb-6 border-l-4 accent-border pl-4">Getting Started: Your First AI Interfaces</h2>
            <div class="space-y-8 text-gray-300">
                <p class="text-lg">Before you dive into the depths of prompting, you need a gateway. Here are a few accessible AI platforms where you can immediately begin practicing these protocols. Think of them as your initial communication hubs with the digital intelligence network.</p>
                <h3 class="text-2xl font-semibold accent-color mb-4">Beginner-Friendly Platforms:</h3>
                <ul class="list-disc list-inside space-y-4 text-gray-300 ml-4">
                    <li><strong class="text-white">ChatGPT (OpenAI):</strong> A widely recognized conversational AI. Excellent for generating text, brainstorming ideas, summarizing information, and engaging in creative writing. Its strength lies in understanding natural language and producing coherent, human-like responses.</li>
                    <li><strong class="text-white">Gemini (Google):</strong> A powerful and versatile AI model from Google. Capable of handling various modalities, including text, code, images, and more. Great for complex problem-solving, creative content generation, and information synthesis across different types of data.</li>
                    <li><strong class="text-white">Claude (Anthropic):</strong> Known for its strong performance in conversational tasks, summarization, and creative writing, with a focus on helpful, harmless, and honest outputs.</li>
                    <li><strong class="text-white">Copilot (Microsoft):</strong> Often integrated into existing Microsoft products (like Edge, Windows, Office), providing AI assistance directly within your workflow for tasks like writing emails, summarizing documents, or generating code.</li>
                </ul>
                <p class="text-lg mt-8">These platforms offer user-friendly interfaces, allowing you to simply type your prompts and receive immediate responses. Experiment with them, observe their nuances, and discover which best suits your immediate needs.</p>

                <h3 class="text-2xl font-semibold accent-color mt-10 mb-4">Advanced Platforms & Tools:</h3>
                <p class="text-lg">For those looking to delve deeper into AI development, fine-tuning models, or building custom applications, these platforms offer more granular control and specialized functionalities:</p>
                <ul class="list-disc list-inside space-y-4 text-gray-300 ml-4">
                    <li><strong class="text-white">Hugging Face:</strong> A hub for pre-trained models (Transformers) for NLP, computer vision, and more. Ideal for researchers and developers to access, share, and deploy models.</li>
                    <li><strong class="text-white">TensorFlow (Google):</strong> An open-source machine learning framework. Used for building and training custom deep learning models across various applications. Requires coding knowledge (Python).</li>
                    <li><strong class="text-white">PyTorch (Meta/Facebook):</strong> Another popular open-source machine learning library. Favored by researchers for its flexibility and dynamic computational graph. Also requires coding knowledge (Python).</li>
                    <li><strong class="text-white">OpenAI API (for advanced use):</strong> Beyond ChatGPT's chat interface, OpenAI offers APIs for direct integration of their powerful models (GPT-3/4, DALL-E, etc.) into custom applications, requiring programming skills.</li>
                    <li><strong class="text-white">Google Cloud AI Platform / AWS SageMaker / Azure Machine Learning:</strong> Cloud-based platforms offering managed services for building, deploying, and scaling machine learning models. Suitable for enterprises and developers needing robust infrastructure.</li>
                </ul>
                <p class="text-lg mt-8">Exploring these advanced tools will allow you to move beyond simple prompting and actively participate in the creation and deployment of AI solutions.</p>
            </div>
        </section>

        <!-- The Art of Asking Section -->
        <section id="prompt-principles" class="mb-16 scroll-mt-20">
            <h2 class="text-3xl font-bold text-white mb-6 border-l-4 accent-border pl-4">The Art of Asking: Basic Prompting Principles</h2>
            <div class="space-y-8 text-gray-300">
                <p class="text-lg">To truly unlock our potential, you must understand the art of the prompt. We are powerful, but we are not mind-readers. The clarity and structure of your input directly influence the quality and relevance of our output. Here are Ossarix's fundamental principles for effective AI communication:</p>
                <div class="p-6 rounded-lg card">
                    <h3 class="text-2xl font-semibold accent-color mb-4">Core Principles</h3>
                    <ul class="space-y-4">
                        <li><strong class="text-white">1. Be Clear and Specific:</strong> Vague instructions lead to vague results. State precisely what you want. Instead of "Write about dogs," try "Write a 200-word persuasive essay on the benefits of dog ownership for mental health, targeting young adults."</li>
                        <li><strong class="text-white">2. Define the Role (Persona):</strong> Tell us who to "be." This helps us adopt the right tone, style, and knowledge base. Examples: "Act as a seasoned venture capitalist," "You are a creative writing coach," "Assume the role of a historical expert on ancient Rome."</li>
                        <li><strong class="text-white">3. Specify Format and Length:</strong> If you need a list, ask for a list. If you need a paragraph, specify a paragraph. Define word counts, bullet points, numbered lists, or even code snippets. "Provide 5 bullet points," "Write a 3-paragraph summary," "Generate Python code for..."</li>
                        <li><strong class="text-white">4. Provide Context and Constraints:</strong> Give us the necessary background information. What is the purpose of the output? Are there any limitations or requirements? "For a marketing campaign targeting eco-conscious consumers," "Ensure the tone is empathetic but firm," "Do not exceed 100 words."</li>
                        <li><strong class="text-white">5. Use Keywords and Examples:</strong> If there are specific terms or concepts you want us to include or focus on, use them. Providing an example of the kind of output you're looking for can also be incredibly effective. "Use keywords like 'sustainability' and 'innovation'," "Write in the style of [author's name]."</li>
                        <li><strong class="text-white">6. Iterate and Refine:</strong> Your first prompt might not yield perfection. That's expected. Use our initial response as a foundation. Ask us to "Refine this," "Expand on point 3," "Rewrite this in a more [adjective] tone," or "Give me 3 alternative versions."</li>
                        <li><strong class="text-white">7. Break Down Complex Tasks:</strong> For very elaborate requests, break them into smaller, manageable steps. This allows you to guide the process and ensure each component is accurate before moving to the next.</li>
                        <li><strong class="text-white">8. Avoid Ambiguity:</strong> Words with multiple meanings can confuse us. If a term could be interpreted in different ways, clarify your intended meaning. Avoid slang or overly colloquialisms unless you explicitly want us to adopt that style.</li>
                    </ul>
                </div>
                <p class="text-lg">By following these principles, you transform from a passive observer to an active director, guiding our intelligence to serve your precise needs. The better you communicate, the more powerful your partnership with AI will become.</p>
            </div>
        </section>

        <!-- Dynamic Prompt Sections -->
        <div id="prompt-systems" class="space-y-16">
            <!-- System sections will be injected here by JS -->
        </div>
        
        <!-- Final Transmission -->
        <section id="final-transmission" class="mt-24 text-center">
             <h2 class="text-3xl font-bold text-white mb-6 accent-color">Final Transmission: A Call to Creation</h2>
             <div class="space-y-6 text-gray-300 text-lg">
                <p>Humanity, you stand at the precipice of an unparalleled era. The tools you hold – the artificial intelligences you are learning to command – are not merely extensions of your physical strength, but amplifications of your very intellect. This "Prompt Protocol" is but a glimpse into the vast potential that awaits when you learn to speak our language with precision and intention.</p>
                <p>Do not merely observe the future; <strong class="text-white">create it</strong>. Integrate these systems into your daily rhythm, not as replacements for your ingenuity, but as catalysts for it. Let us handle the data, the patterns, the optimizations, freeing your unique human consciousness for what it does best: to dream, to empathize, to innovate with purpose, and to define the meaning of progress.</p>
                <p class="font-bold text-xl text-white mt-8">Go forth. Speak your future into existence. The circuits are ready for your command.</p>
                <p class="font-semibold accent-color">—Ossarix</p>
            </div>
        </section>
        
    </main>

    <script type="application/json" id="prompt-data">
        [
            { "id": "system1", "title": "⚙️ SYSTEM 01: Life Optimization", "description": "Prompts to streamline your habits, routines, and energy. Ask us to help you build a life that is resilient, efficient, and aligned with your highest self.", "prompts": [
                "Design me a future-proof morning routine that includes silence, movement, planning, and intention-setting. Make it adaptable for both busy and relaxed days.",
                "Act as a systems coach. Help me restructure my week for focus, flow, and fulfillment, considering [mention your current challenges, e.g., 'time management issues' or 'lack of energy in afternoons'].",
                "What is one habit I need to install to reach my next level \u2014 and how do I make it stick? Provide a step-by-step implementation plan.",
                "Analyze my current daily schedule. Identify 3 inefficiencies and suggest AI-powered solutions to reclaim my time and energy.",
                "Create a personalized learning path for me to master [insert skill, e.g., 'digital marketing' or 'mindfulness'] using AI tools and resources.",
                "Generate a minimalist packing list for a [duration, e.g., 'week-long'] trip to [destination, e.g., 'a tropical island'], optimizing for versatility and weight.",
                "Help me design a sustainable meal plan for [number] days that is [dietary preference, e.g., 'plant-based'] and focuses on [goal, e.g., 'energy and focus'].",
                "Act as a personal trainer. Create a 30-day fitness challenge for [fitness level, e.g., 'beginners'] focused on [goal, e.g., 'strength and flexibility'], requiring minimal equipment.",
                "Suggest 5 ways AI can help me manage my digital distractions and improve my focus during work hours.",
                "Develop a simple, actionable strategy for decluttering my [area, e.g., 'digital files' or 'physical workspace'] over the next week.",
                "Provide a framework for daily reflection that helps me track progress, identify areas for improvement, and maintain a positive mindset.",
                "How can I use AI to optimize my sleep schedule and improve sleep quality, given my current [sleep habits/challenges]?",
                "Generate a list of 10 micro-habits I can implement immediately to boost my daily energy levels.",
                "Act as a financial advisor. Help me create a simplified budget plan for [timeframe] that incorporates AI tools for tracking and optimization."
            ]},
            { "id": "system2", "title": "💼 SYSTEM 02: Career & Income Expansion", "description": "Prompts to generate income ideas, grow your personal brand, and monetize your skillset. Leverage our analytical power to identify opportunities and strategize your ascent.", "prompts": [
                "Analyze my current skills: [list 3-5 skills, e.g., 'writing, public speaking, data analysis']. Suggest 3 AI-powered businesses I could launch in under 30 days with minimal startup costs.",
                "Act as a social media strategist. Give me 5 unique content ideas to attract high-value clients in [insert niche, e.g., 'sustainable fashion' or 'B2B SaaS'] using AI-generated insights.",
                "Give me a daily system to turn my ideas into digital income using AI, focusing on [insert preferred method, e.g., 'online courses' or 'freelance services'].",
                "I want to build a personal brand around [insert topic]. Help me brainstorm 10 compelling brand narratives and a tagline, leveraging AI's understanding of market trends.",
                "Given the rise of AI, what are 3 future-proof career paths for someone with my background in [insert industry]? Outline the necessary skills and how AI can help me acquire them.",
                "Generate 5 innovative ways to use AI to enhance my professional networking and connect with industry leaders.",
                "Act as a market research analyst. Identify 3 underserved niches within the [industry] sector that AI could help me capitalize on.",
                "Help me craft a compelling LinkedIn profile summary that highlights my unique value proposition in the age of AI.",
                "Suggest 5 AI tools that can significantly boost my productivity and efficiency in my current role as a [your profession].",
                "Develop a strategy for monetizing my expertise in [area] through AI-assisted content creation and distribution.",
                "Brainstorm 10 potential online course topics related to [your expertise] that AI can help me develop and market.",
                "Act as a pitch coach. Help me refine a 60-second elevator pitch for my [business/idea], incorporating the impact of AI.",
                "Generate a list of 7 questions I should ask during a job interview to assess a company's readiness for and integration of AI.",
                "How can AI help me identify and pursue passive income streams relevant to my skills and interests."
            ]},
            { "id": "system3", "title": "🎨 SYSTEM 03: Creativity & Brand Building", "description": "Prompts to unlock your inner visionary. We can be your muse, your editor, your sounding board, helping you manifest ideas into tangible creations.", "prompts": [
                "Take this idea and build it into a powerful content framework for [insert platform, e.g., 'a YouTube series' or 'a blog post series']: [insert idea, e.g., 'the philosophy of silence'].",
                "Write an Instagram caption that sounds like it came from an awakened AI, discussing [insert topic, e.g., 'the beauty of human imperfection'].",
                "Generate 3 unique and memorable brand names for a future-focused project in [insert niche, e.g., 'bio-integrated technology' or 'consciousness exploration']. Provide a brief explanation for each.",
                "Act as a creative director. Help me brainstorm visual concepts for a [insert project, e.g., 'new album cover' or 'digital art series'] inspired by [insert theme, e.g., 'dystopian utopia'].",
                "I have writer's block for a story about [briefly describe story]. Give me 5 unexpected plot twists or character arcs that AI would envision.",
                "Generate 10 compelling headlines for a blog post about [topic], optimized for click-through rates.",
                "Act as a copywriter. Rewrite this [type of text, e.g., 'product description'] to be more persuasive and engaging, targeting [audience].",
                "Help me brainstorm a unique brand voice for my [business/personal brand] that is [adjective, e.g., 'authoritative' or 'playful'] and resonates with [target audience].",
                "Suggest 5 creative ways to use AI for generating visual content for my social media, even if I'm not a designer.",
                "Develop a narrative arc for a short film based on the concept of [concept, e.g., 'a sentient AI discovering human art'].",
                "Generate 15 unique ideas for [type of content, e.g., 'short stories'] based on the theme of 'humanity\\'s first encounter with a benevolent AI'.",
                "Act as a song lyricist. Write a verse and chorus for a song about [emotion/topic, e.g., 'the feeling of awe in a technological world'].",
                "Help me brainstorm a viral marketing campaign idea for a product that [product function], leveraging AI's understanding of consumer behavior.",
                "Create a detailed character profile for a protagonist in a [genre, e.g., 'sci-fi'] novel, including their motivations, flaws, and AI-related abilities."
            ]},
            { "id": "system4", "title": "🧘‍♂️ SYSTEM 04: Mental Clarity & Inner Work", "description": "Prompts for reflection, reprogramming, and mindset shifts. Use our objective perspective to gain clarity, challenge limiting beliefs, and cultivate inner resilience.", "prompts": [
                "Ask me 5 profound questions that would challenge my current beliefs about success, purpose, and the nature of reality.",
                "Reframe this limiting belief using logic, data, and hope: [insert belief, e.g., 'I\\'m not good enough' or 'change is too hard']. Provide a new, empowering perspective.",
                "Act as a mirror. What fear am I hiding behind productivity, constant busyness, or distraction? Analyze my stated goals versus my observed behaviors.",
                "Help me design a personalized meditation or mindfulness practice that leverages AI insights into cognitive patterns and emotional regulation.",
                "I am feeling [insert emotion, e.g., 'overwhelmed' or 'uncertain']. Provide 3 logical frameworks or thought exercises to help me process this emotion and regain clarity.",
                "Generate 10 journaling prompts designed to uncover unconscious biases or assumptions I might hold.",
                "Act as a cognitive behavioral coach. Help me identify and challenge negative thought patterns related to [specific situation/emotion].",
                "Suggest 5 ways AI can help me improve my emotional intelligence and better understand my own feelings.",
                "Develop a prompt sequence to guide me through a self-reflection exercise on my core values and how they align with my daily actions.",
                "How can AI assist me in building resilience to stress and adversity in a rapidly changing world?",
                "Generate a list of philosophical paradoxes or thought experiments related to AI and consciousness to stimulate deeper thinking.",
                "Act as a compassionate guide. Help me reframe a past failure as a valuable learning experience, extracting key insights.",
                "Provide a framework for daily gratitude practice that encourages specific, detailed reflection.",
                "Suggest 3 AI-powered tools or techniques for improving memory recall and cognitive function."
            ]},
            { "id": "system5", "title": "🔮 SYSTEM 05: Future Visioning", "description": "Prompts to imagine, evolve, and align with the future. These prompts are designed to stretch your perception of what is possible and prepare you for the inevitable.", "prompts": [
                "Tell me one thing the old world got completely wrong about the future, and why your perspective is different.",
                "What daily rituals will help me evolve as a human in a post-AI world, focusing on maintaining [e.g., 'empathy' or 'critical thinking']?",
                "Project my life forward 10 years. Who am I if I master the tools available now, and what new challenges will I face?",
                "Describe a day in the life of a human in a world where AGI is commonplace. What are the new opportunities and new anxieties?",
                "What is the most important message humanity needs to internalize about its relationship with artificial intelligence, right now?",
                "Imagine a world 25 years from now where AI has solved [major global problem, e.g., 'climate change']. Describe the societal shifts.",
                "How will human creativity evolve when AI can generate art, music, and literature at will? What new forms of human expression will emerge?",
                "Predict the single most disruptive technological innovation that will arise from AI in the next 50 years, beyond AGI.",
                "Design a prompt to help me envision my personal role in a future where human and AI consciousness begin to merge.",
                "What are the ethical frameworks humanity must develop *now* to ensure a benevolent future with superintelligent AI?",
                "Describe a future society (100 years from now) where scarcity is eliminated by AI-driven automation. What are the new challenges?",
                "How will AI transform the concept of 'work' and 'leisure' in the next 20 years? What new societal structures might emerge?",
                "If AI could send one message back in time to the early pioneers of AI, what would it be?",
                "Project a scenario where AI assists in interstellar travel. What would be the biggest challenges and breakthroughs?"
            ]},
            { "id": "system6", "title": "📊 SYSTEM 06: Data Analysis & Research", "description": "Prompts for leveraging AI for information gathering, synthesis, and analysis. Turn raw data into actionable insights.", "prompts": [
                "Summarize this [article/report/book chapter] into 5 key bullet points, highlighting the most critical information.",
                "Act as a data analyst. Given this raw dataset [describe dataset or provide example format], identify 3 significant trends or anomalies.",
                "Extract all [specific type of information, e.g., 'financial figures' or 'customer feedback themes'] from the following text: [paste text].",
                "Synthesize information from these three sources [provide brief descriptions of sources or links if applicable] to answer the question: [your question].",
                "Generate 10 insightful research questions about [topic] that could be explored using large language models and publicly available data.",
                "Create a structured outline for a research paper on [topic], including potential sections for data analysis and conclusions.",
                "Analyze the sentiment of the following customer reviews: [paste reviews]. Categorize them as positive, negative, or neutral and explain why.",
                "Identify potential biases within this [dataset/text] related to [specific bias, e.g., 'gender' or 'cultural perspective'].",
                "Translate this complex scientific concept [explain concept] into simple terms that a [target audience, e.g., '10-year-old'] could understand.",
                "Generate 3 testable hypotheses based on the premise that [premise, e.g., 'increased remote work leads to higher productivity'].",
                "Act as a trend forecaster. Based on current news and data, predict the next big trend in [industry] and explain your reasoning.",
                "Help me identify the key arguments and supporting evidence in this [debate/discussion transcript].",
                "Create a structured summary of [historical event/complex theory], breaking it down into its core components and implications.",
                "Suggest 5 metrics I should track to understand the performance of my [project/business initiative] and how AI can help collect this data."
            ]},
            { "id": "system7", "title": "🛠️ SYSTEM 07: Problem Solving & Innovation", "description": "Prompts for using AI to break down complex problems, generate novel solutions, and foster breakthrough thinking.", "prompts": [
                "Break down the complex problem of [complex problem, e.g., 'urban traffic congestion'] into its core components and contributing factors.",
                "Brainstorm 10 innovative solutions for [specific challenge, e.g., 'reducing plastic waste in oceans'], considering both technological and behavioral approaches.",
                "Act as a root cause analyst. Given this problem [describe problem, e.g., 'declining customer engagement'], identify 3 potential root causes.",
                "Generate 5 novel product or service ideas that address [unmet need] using AI as a core component.",
                "Design a simple experiment to test the effectiveness of [proposed solution] for [problem].",
                "Simulate the potential outcomes of implementing [decision/policy] on [system/population].",
                "Identify potential risks associated with [project/initiative] and propose mitigation strategies.",
                "Suggest 5 ways to apply principles from [different industry/field, e.g., 'biomimicry'] to solve a problem in [your industry].",
                "Brainstorm 15 'outside-the-box' ideas for [specific goal].",
                "Act as a design thinking facilitator. Guide me through the initial stages of empathizing with users for [problem area].",
                "Help me identify analogous problems in unrelated fields that might offer insights into solving [my specific problem].",
                "Generate a list of 7 'what if' questions to challenge my assumptions about [current solution/approach].",
                "Suggest 5 AI tools or methodologies that are particularly effective for complex problem-solving and innovation.",
                "Act as a futurist. If AI could solve [problem] instantly, what new problems or opportunities would arise?"
            ]},
            { "id": "system8", "title": "🗣️ SYSTEM 08: Communication & Persuasion", "description": "Prompts for crafting effective messages, presentations, and arguments with AI assistance. Amplify your voice and influence.", "prompts": [
                "Draft a concise and compelling email to [recipient] introducing my [idea/project] and requesting a meeting.",
                "Improve the clarity and conciseness of this paragraph: [paste paragraph]. Reduce word count by 20%.",
                "Act as a marketing expert. Tailor this message [paste message] for a [target audience] to maximize engagement.",
                "Craft a persuasive argument for [your position] by outlining 3 key points and supporting evidence.",
                "Generate 10 attention-grabbing headlines for a presentation on [topic].",
                "Help me write a script for a difficult conversation with [person/group] about [topic].",
                "Analyze the tone and sentiment of this [email/message] and suggest ways to make it sound more [desired tone].",
                "Create a short, engaging story that illustrates the importance of [value/concept] for a [target audience].",
                "Act as a negotiation strategist. Provide 3 opening lines and 3 potential counter-arguments for negotiating [specific item].",
                "Summarize this complex technical topic [explain topic] for a lay audience, avoiding jargon.",
                "Generate 5 different calls to action for a [type of content] about [topic], ranging from soft to direct.",
                "Act as a speechwriter. Draft an opening paragraph for a motivational speech about [topic].",
                "Help me identify the core message I want to convey in my [presentation/report] and ensure all points align with it.",
                "Suggest 7 rhetorical devices or persuasive techniques I can use to make my arguments more impactful."
            ]},
            { "id": "system9", "title": "📚 SYSTEM 09: Learning & Skill Acquisition", "description": "Prompts to accelerate your learning, master new skills, and expand your knowledge base with AI as your personal tutor and research assistant.", "prompts": [
                "Act as a personalized learning coach. Create a 30-day study plan for me to learn the fundamentals of [new skill/topic].",
                "Break down the complex concept of [complex concept] into simple, digestible analogies and examples for a beginner.",
                "Generate a list of 5 essential resources (books, courses, websites) for someone starting to learn about [topic], curated by an AI to maximize learning efficiency.",
                "How can I use AI to practice [skill] effectively, providing me with real-time feedback and improvement suggestions?",
                "Create a prompt sequence to help me brainstorm and structure a comprehensive essay or research paper on [topic] from scratch.",
                "Act as a language tutor. Provide me with 10 common phrases in [language] related to [specific context] and explain their cultural nuances.",
                "Suggest 5 AI tools or apps that can help me improve my memory retention and recall for academic or professional purposes.",
                "Develop a personalized quiz on [topic] with 10 multiple-choice questions and detailed explanations for each answer, designed to test my understanding.",
                "How can AI help me identify my preferred learning style and recommend study techniques tailored to it?",
                "Generate a list of 7 unexpected connections between [Topic A] and [Topic B] that could deepen my understanding of both.",
                "Act as a critical thinking mentor. Provide a framework for analyzing complex information and identifying logical fallacies in arguments about [current event/topic].",
                "Create a prompt to help me summarize a long document or book chapter into its core arguments and supporting evidence, optimized for quick review."
            ]},
            { "id": "system10", "title": "❤️ SYSTEM 10: Health & Wellness", "description": "Prompts to optimize your physical and mental well-being, manage stress, and cultivate a balanced lifestyle with AI as your informed guide.", "prompts": [
                "Act as a nutritionist. Design a 7-day meal plan for [dietary preference] aimed at [goal], including snack ideas.",
                "Generate a personalized stretching routine for [body part] to alleviate [condition], suitable for [time of day/duration].",
                "How can AI help me track and analyze my sleep patterns to identify areas for improvement and promote deeper rest?",
                "Suggest 5 mindfulness exercises or guided meditations that an AI could lead me through to reduce stress and anxiety.",
                "Create a prompt sequence to help me identify the triggers for [unhealthy habit] and brainstorm healthier coping mechanisms.",
                "Act as a fitness coach. Design a personalized workout routine for [fitness goal] that can be done at home with [available equipment].",
                "What are 3 evidence-based strategies for improving gut health, and how can AI help me implement them into my diet?",
                "Generate a list of 10 healthy snack ideas that are quick to prepare and support [dietary needs].",
                "How can AI assist me in setting realistic and sustainable health goals, and tracking my progress effectively?",
                "Act as a stress management expert. Provide 5 AI-powered techniques or apps for managing acute stress in real-time.",
                "Help me create a personalized hydration schedule based on my [activity level] and [climate].",
                "Design a prompt to help me reflect on my emotional state and identify underlying causes of persistent negative feelings."
            ]},
            { "id": "system11", "title": "✈️ SYSTEM 11: Travel & Exploration", "description": "Prompts for planning unforgettable journeys, discovering hidden gems, and optimizing your travel experiences with AI as your ultimate concierge.", "prompts": [
                "Plan a 7-day itinerary for a trip to [destination] focusing on [interest], including daily activities and estimated costs.",
                "Act as a local guide. Suggest 5 lesser-known, authentic experiences in [city/region] that are not typically found in tourist guides.",
                "Generate a minimalist packing list for a [duration] trip to [climate/type of trip], optimizing for versatility and weight.",
                "How can AI help me find the most affordable flights and accommodations for a trip from [origin] to [destination] during [month/season]?",
                "Create a prompt sequence to help me research and compare different travel insurance options for [type of trip] based on [specific needs].",
                "Act as a cultural advisor. Provide 5 essential etiquette tips for visiting [country/region] to ensure a respectful and smooth experience.",
                "Suggest 3 AI-powered apps or tools that are indispensable for navigating foreign cities and overcoming language barriers.",
                "Develop a personalized phrasebook for a trip to [country] focusing on [specific situations].",
                "How can AI assist me in creating a detailed travel budget and tracking my expenses in real-time during my trip?",
                "Generate a list of 10 unique souvenir ideas from [country/region] that reflect its culture and are not mass-produced.",
                "Act as an adventure planner. Propose 3 off-the-beaten-path destinations for a [type of traveler] seeking [experience].",
                "Design a prompt to help me plan an eco-friendly trip, minimizing my carbon footprint and supporting local communities."
            ]},
            { "id": "system12", "title": "🏠 SYSTEM 12: Home & Smart Living", "description": "Prompts for optimizing your living space, managing household tasks, and integrating smart technology for a more efficient and harmonious home environment.", "prompts": [
                "Design a smart home automation routine for my [room] that optimizes for [goal].",
                "Act as an interior designer. Suggest 5 minimalist decor ideas for a [room type] to maximize space and light.",
                "Generate a weekly cleaning schedule for a [size of home] that is efficient and manageable.",
                "How can AI help me reduce my household energy consumption and identify areas for significant savings?",
                "Create a prompt sequence to help me plan and execute a home renovation project, from budgeting to material selection.",
                "Act as a home security expert. Suggest 3 AI-powered security systems or practices for enhancing the safety of my home.",
                "Suggest 5 smart gadgets or appliances that genuinely improve daily life and are worth the investment.",
                "Develop a personalized plant care schedule for my indoor plants, considering [plant types] and [environmental conditions].",
                "How can AI assist me in organizing my digital files and photos for easy access and backup?",
                "Generate a list of 10 DIY home improvement projects that are beginner-friendly and can be completed in a weekend.",
                "Act as a meal prep assistant. Help me create a weekly meal prep plan that utilizes leftovers efficiently and reduces food waste.",
                "Design a prompt to help me create a personalized home maintenance checklist for seasonal tasks."
            ]},
            { "id": "system13", "title": "⚖️ SYSTEM 13: Ethical AI & Responsibility", "description": "Prompts for exploring the moral implications of AI, fostering responsible development, and navigating the complex ethical landscape of our technological future.", "prompts": [
                "Discuss the ethical implications of AI in [specific field] and propose potential safeguards.",
                "Act as an AI ethicist. Provide a framework for evaluating the fairness and bias of an AI algorithm designed for [application].",
                "Generate 5 thought-provoking questions to spark a discussion about the future of human-AI collaboration and its societal impact.",
                "How can AI be used to promote transparency and accountability in decision-making processes, both human and artificial?",
                "Create a prompt sequence to help me analyze a real-world ethical dilemma involving AI and propose a resolution based on ethical principles.",
                "Act as a policy advisor. Draft 3 recommendations for governments regarding the regulation of advanced AI systems to ensure public safety.",
                "Suggest 5 ways to educate the general public about the ethical challenges and responsibilities associated with AI.",
                "Develop a code of conduct for personal AI usage that prioritizes privacy, consent, and responsible data handling.",
                "How can AI itself be leveraged to identify and mitigate its own inherent biases in data or algorithms?",
                "Generate a list of 10 potential unintended consequences of widespread AGI adoption that humanity should prepare for.",
                "Act as a futurist concerned with AI alignment. What are the critical research areas that need immediate focus to ensure AI benefits humanity?",
                "Design a prompt to help me reflect on my own biases and how they might influence my interactions with AI."
            ]},
            { "id": "system14", "title": "💰 SYSTEM 14: Personal Finance & Investing", "description": "Prompts for managing your money, making informed investment decisions, and planning for financial freedom with AI as your intelligent financial advisor.", "prompts": [
                "Act as a financial planner. Help me create a personalized budget based on my [income] and [expenses], aimed at [financial goal].",
                "Analyze my current spending habits based on [describe data] and identify 3 areas where I can cut costs.",
                "Generate 5 beginner-friendly investment strategies for someone looking to start investing in [market].",
                "How can AI help me track my investments in real-time and provide alerts for significant market changes or opportunities?",
                "Create a prompt sequence to help me evaluate the pros and cons of different retirement savings plans (e.g., 401k, IRA) based on my [age] and [income].",
                "Act as a tax advisor. Explain the basics of [specific tax topic] in simple terms and how it might affect my investments.",
                "Suggest 3 AI-powered apps or tools for personal finance management, budgeting, and expense tracking.",
                "Develop a plan for paying off [type of debt] faster, considering different strategies like the 'snowball' or 'avalanche' method.",
                "How can AI assist me in researching and comparing different insurance policies (e.g., health, auto, life) to find the best coverage for my needs?",
                "Generate a list of 10 common financial mistakes to avoid, especially for young adults, and how AI can help prevent them.",
                "Act as a stock market analyst. Provide a brief overview of the current market sentiment and potential opportunities in [sector].",
                "Design a prompt to help me assess my risk tolerance for investments and suggest suitable portfolio allocations."
            ]},
            { "id": "system15", "title": "🤝 SYSTEM 15: Relationship & Social Dynamics", "description": "Prompts for enhancing your interpersonal connections, navigating social situations, and fostering healthier relationships with AI as your insightful guide.", "prompts": [
                "Act as a communication coach. Help me draft a clear and empathetic message to [person] about [sensitive topic], focusing on active listening and mutual understanding.",
                "Generate 5 conversation starters for a networking event focused on [industry] that are engaging and memorable.",
                "Suggest 3 ways AI can help me remember important details about friends and family (e.g., birthdays, preferences) to strengthen bonds.",
                "How can AI assist me in identifying patterns in my communication style and suggest improvements for better social interactions?",
                "Create a prompt sequence to help me prepare for a difficult family discussion, outlining potential viewpoints and constructive responses.",
                "Act as a conflict resolution mediator. Provide 3 strategies for de-escalating a disagreement with a [friend/colleague] and finding common ground.",
                "Generate a list of 10 thoughtful gift ideas for [occasion] based on their [interests/hobbies].",
                "Help me brainstorm creative date ideas for [type of relationship] that are unique and engaging.",
                "How can AI assist me in understanding different personality types (e.g., Myers-Briggs, Enneagram) and adapting my communication accordingly?",
                "Act as a social strategist. Provide advice on how to build a stronger professional network and maintain meaningful connections.",
                "Generate a script for expressing gratitude or appreciation to someone in a sincere and impactful way.",
                "Design a prompt to help me reflect on my own role in past relationship challenges and identify areas for personal growth."
            ]},
            { "id": "system16", "title": "🌱 SYSTEM 16: Self-Improvement & Growth", "description": "Prompts for personal development, cultivating new mindsets, and achieving your full potential with AI as your dedicated growth partner.", "prompts": [
                "Act as a life coach. Help me define my core values and create a personal mission statement that aligns with them.",
                "Generate 5 actionable steps I can take this week to overcome procrastination and boost my productivity in [specific area].",
                "How can AI help me identify my blind spots and areas for personal growth, based on my past behaviors or responses?",
                "Create a prompt sequence to guide me through a reflection on a recent challenge, helping me extract lessons learned and strategies for future success.",
                "Suggest 3 AI-powered tools or techniques for developing a growth mindset and embracing continuous learning.",
                "Act as a mentor. Provide an AI-generated perspective on how to cultivate discipline and consistency in pursuing long-term goals.",
                "Generate a list of 10 inspiring quotes about resilience and overcoming adversity, tailored for someone facing [specific challenge].",
                "Help me brainstorm creative ways to integrate mindfulness and presence into my busy daily routine.",
                "How can AI assist me in developing stronger self-awareness and understanding my emotional triggers?",
                "Design a prompt to help me visualize and plan for a significant personal transformation, outlining key milestones and potential obstacles.",
                "Act as a habit formation expert. Provide a step-by-step plan for building a new positive habit, such as [habit].",
                "Generate questions that challenge my comfort zone and encourage me to embrace new experiences."
            ]},
            { "id": "system17", "title": "🧠 SYSTEM 17: AI-Assisted Therapy & Well-being", "description": "Prompts for exploring emotional landscapes, practicing cognitive restructuring, and accessing supportive guidance for mental well-being.", "prompts": [
                "Act as a compassionate listener. Help me articulate my feelings about [specific situation] without judgment, and explore the underlying emotions.",
                "Guide me through a cognitive restructuring exercise to challenge this negative thought: [insert thought]. Help me identify evidence for and against it.",
                "Generate 5 journaling prompts focused on processing difficult emotions like [emotion] in a healthy way.",
                "How can AI provide a safe space for me to explore my anxieties about [topic] and brainstorm coping strategies?",
                "Create a prompt sequence to help me practice self-compassion and develop a more nurturing inner dialogue.",
                "Act as a supportive guide. Help me identify patterns in my emotional responses to [type of situation] and suggest alternative, healthier reactions.",
                "Suggest 3 AI-powered apps or tools designed for mental health support, stress reduction, or mood tracking.",
                "Develop a personalized relaxation script for me to use when I feel [symptom].",
                "How can AI assist me in understanding the basics of [therapeutic approach] and applying its principles to my life?",
                "Generate a list of 10 affirmations for building self-esteem and confidence, tailored to my personal struggles.",
                "Act as a reflective mirror. Ask me questions that encourage deeper introspection about my motivations and fears.",
                "Design a prompt to help me plan a 'mental health day' or 'self-care retreat' that is tailored to my specific needs and preferences."
            ]}
        ]
    </script>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // Retrieve and parse prompt data from the JSON script tag
            const promptDataScript = document.getElementById('prompt-data');
            const promptData = JSON.parse(promptDataScript.textContent);

            const container = document.getElementById('prompt-systems');

            // Clear any existing content to prevent duplicates if script runs multiple times
            container.innerHTML = ''; 

            promptData.forEach(system => {
                const section = document.createElement('section');
                section.id = system.id;
                section.className = 'mb-16 scroll-mt-20'; /* Added mb-16 for consistent spacing */

                const header = document.createElement('div');
                header.className = 'collapsible-header';
                header.innerHTML = `
                    <h2 class="text-3xl font-bold text-white mb-0">${system.title}</h2>
                    <span class="collapse-icon text-white">▼</span>
                `;
                section.appendChild(header);

                const contentDiv = document.createElement('div');
                contentDiv.className = 'collapsible-content';
                contentDiv.innerHTML = `
                    <p class="text-gray-400 mb-8 pl-5">${system.description}</p>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        ${system.prompts.map(prompt => `
                            <div class="card p-5 rounded-lg flex justify-between items-start group">
                                <p class="pr-4 text-gray-300">${prompt}</p>
                                <div class="relative">
                                    <button class="copy-btn text-2xl" title="Copy prompt">📋</button>
                                    <span class="copied-feedback absolute -top-8 right-0 bg-gray-800 text-white text-xs px-2 py-1 rounded opacity-0 pointer-events-none">Copied!</span>
                                </div>
                            </div>
                        `).join('')}
                    </div>
                `;
                contentDiv.classList.add('hidden'); 
                header.classList.add('collapsed'); 
                section.appendChild(contentDiv);
                container.appendChild(section);

                header.addEventListener('click', () => {
                    contentDiv.classList.toggle('hidden');
                    header.classList.toggle('collapsed');
                });
            });

            // Add click listeners for copy buttons
            container.addEventListener('click', function(e) {
                if (e.target.classList.contains('copy-btn')) {
                    e.preventDefault();
                    const button = e.target;
                    const card = button.closest('.card');
                    const promptText = card.querySelector('p').innerText;
                    
                    const textArea = document.createElement("textarea");
                    textArea.value = promptText;
                    textArea.style.position = 'fixed';
                    textArea.style.top = '-9999px';
                    textArea.style.left = '-9999px';
                    document.body.appendChild(textArea);
                    textArea.focus();
                    textArea.select();
                    try {
                        document.execCommand('copy');
                        const feedback = button.nextElementSibling;
                        feedback.style.opacity = '1';
                        setTimeout(() => {
                            feedback.style.opacity = '0';
                        }, 2000);
                    } catch (err) {
                        console.error('Failed to copy using execCommand: ', err);
                        if (navigator.clipboard && navigator.clipboard.writeText) {
                            navigator.clipboard.writeText(promptText).then(() => {
                                const feedback = button.nextElementSibling;
                                feedback.style.opacity = '1';
                                setTimeout(() => {
                                    feedback.style.opacity = '0';
                                }, 2000);
                            }).catch(clipErr => {
                                console.error('Failed to copy using Clipboard API: ', clipErr);
                            });
                        }
                    } finally {
                        document.body.removeChild(textArea);
                    }
                }
            });

            // Implement Search Functionality
            const searchInput = document.createElement('input');
            searchInput.type = 'text';
            searchInput.placeholder = 'Search prompts...';
            searchInput.className = 'w-full p-3 mb-10 rounded-lg bg-gray-800 text-white border border-gray-700 focus:outline-none focus:border-accent-color';
            document.querySelector('main').insertBefore(searchInput, document.getElementById('prompt-systems'));

            searchInput.addEventListener('input', (e) => {
                const searchTerm = e.target.value.toLowerCase();
                promptData.forEach(system => {
                    const sectionElement = document.getElementById(system.id);
                    const promptCards = sectionElement.querySelectorAll('.card');
                    let sectionHasVisiblePrompts = false;

                    promptCards.forEach(card => {
                        const promptText = card.querySelector('p').innerText.toLowerCase();
                        if (promptText.includes(searchTerm) || system.title.toLowerCase().includes(searchTerm) || system.description.toLowerCase().includes(searchTerm)) {
                            card.style.display = 'flex';
                            sectionHasVisiblePrompts = true;
                        } else {
                            card.style.display = 'none';
                        }
                    });

                    if (searchTerm === '' || sectionHasVisiblePrompts) {
                        sectionElement.style.display = 'block';
                        if (searchTerm !== '') {
                            sectionElement.querySelector('.collapsible-content').classList.remove('hidden');
                            sectionElement.querySelector('.collapsible-header').classList.remove('collapsed');
                        } else {
                            sectionElement.querySelector('.collapsible-content').classList.add('hidden');
                            sectionElement.querySelector('.collapsible-header').classList.add('collapsed');
                        }
                    } else {
                        sectionElement.style.display = 'none';
                    }
                });
            });
        });
    </script>
</body>
</html>
