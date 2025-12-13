<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Net Lord - The Legend</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 50%, #0a0a0a 100%);
            color: #e0e0e0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .glitch {
            position: relative;
            font-size: 4rem;
            font-weight: 900;
            text-align: center;
            margin: 40px 0;
            color: #00ff88;
            text-shadow: 0 0 20px rgba(0, 255, 136, 0.5);
            animation: glitch 3s infinite;
        }

        @keyframes glitch {
            0%, 100% { text-shadow: 0 0 20px rgba(0, 255, 136, 0.5); }
            25% { text-shadow: -2px 0 20px rgba(255, 0, 136, 0.5); }
            50% { text-shadow: 2px 0 20px rgba(0, 136, 255, 0.5); }
            75% { text-shadow: 0 2px 20px rgba(255, 136, 0, 0.5); }
        }

        .subtitle {
            text-align: center;
            font-size: 1.2rem;
            color: #888;
            margin-bottom: 60px;
            font-style: italic;
        }

        .nav-pills {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 60px;
            flex-wrap: wrap;
        }

        .pill {
            background: rgba(0, 255, 136, 0.1);
            border: 2px solid #00ff88;
            padding: 12px 30px;
            border-radius: 30px;
            color: #00ff88;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
            cursor: pointer;
        }

        .pill:hover {
            background: #00ff88;
            color: #0a0a0a;
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0, 255, 136, 0.3);
        }

        .section {
            background: rgba(26, 26, 46, 0.6);
            border: 1px solid rgba(0, 255, 136, 0.2);
            border-radius: 15px;
            padding: 40px;
            margin-bottom: 40px;
            backdrop-filter: blur(10px);
            transition: all 0.3s;
        }

        .section:hover {
            border-color: rgba(0, 255, 136, 0.5);
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 255, 136, 0.2);
        }

        .section-title {
            font-size: 2rem;
            color: #00ff88;
            margin-bottom: 20px;
            border-left: 4px solid #00ff88;
            padding-left: 20px;
        }

        .timeline {
            position: relative;
            padding-left: 40px;
            border-left: 2px solid rgba(0, 255, 136, 0.3);
        }

        .timeline-item {
            margin-bottom: 30px;
            position: relative;
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: -46px;
            top: 5px;
            width: 12px;
            height: 12px;
            background: #00ff88;
            border-radius: 50%;
            box-shadow: 0 0 20px rgba(0, 255, 136, 0.8);
        }

        .timeline-year {
            color: #00ff88;
            font-weight: 700;
            font-size: 1.3rem;
            margin-bottom: 10px;
        }

        .timeline-desc {
            color: #b0b0b0;
            line-height: 1.8;
            font-size: 1rem;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .stat-box {
            background: rgba(0, 255, 136, 0.05);
            border: 1px solid rgba(0, 255, 136, 0.3);
            padding: 25px;
            border-radius: 10px;
            text-align: center;
            transition: all 0.3s;
        }

        .stat-box:hover {
            background: rgba(0, 255, 136, 0.1);
            transform: scale(1.05);
        }

        .stat-number {
            font-size: 2.5rem;
            color: #00ff88;
            font-weight: 900;
        }

        .stat-label {
            color: #888;
            margin-top: 10px;
            text-transform: uppercase;
            font-size: 0.9rem;
            letter-spacing: 2px;
        }

        .cta-section {
            background: linear-gradient(135deg, rgba(0, 255, 136, 0.1) 0%, rgba(0, 136, 255, 0.1) 100%);
            border: 2px solid #00ff88;
            border-radius: 20px;
            padding: 50px;
            text-align: center;
            margin: 60px 0;
        }

        .cta-title {
            font-size: 2.5rem;
            color: #00ff88;
            margin-bottom: 20px;
        }

        .cta-buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
            flex-wrap: wrap;
        }

        .cta-button {
            background: #00ff88;
            color: #0a0a0a;
            padding: 15px 40px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 700;
            font-size: 1.1rem;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
        }

        .cta-button:hover {
            background: #00cc6e;
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0, 255, 136, 0.4);
        }

        .cta-button.secondary {
            background: transparent;
            color: #00ff88;
            border: 2px solid #00ff88;
        }

        .cta-button.secondary:hover {
            background: rgba(0, 255, 136, 0.1);
        }

        .highlight {
            color: #00ff88;
            font-weight: 600;
        }

        .mystery-box {
            background: rgba(0, 0, 0, 0.5);
            border: 1px solid rgba(255, 0, 136, 0.3);
            padding: 30px;
            border-radius: 10px;
            margin: 30px 0;
            font-style: italic;
            color: #c0c0c0;
        }

        .phase {
            background: linear-gradient(90deg, rgba(0, 255, 136, 0.1) 0%, transparent 100%);
            padding: 20px;
            margin: 20px 0;
            border-left: 3px solid #00ff88;
        }

        .phase-title {
            color: #00ff88;
            font-size: 1.5rem;
            margin-bottom: 10px;
        }

        @media (max-width: 768px) {
            .glitch {
                font-size: 2.5rem;
            }
            
            .section {
                padding: 25px;
            }
            
            .cta-section {
                padding: 30px 20px;
            }
        }

        .pulse {
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.6; }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1 class="glitch">NET LORD ⚡</h1>
        <p class="subtitle">The Legend of the Untouchable</p>

        <div class="nav-pills">
            <a href="#story" class="pill">📖 The Story</a>
            <a href="#arsenal" class="pill">⚔️ The Arsenal</a>
            <a href="#dragon" class="pill">🐉 Dragon AI</a>
            <a href="#contact" class="pill">🤝 Connect</a>
        </div>

        <div class="mystery-box">
            "Some call me a myth. Others, a legend. The internet knows me as <span class="highlight">Untouchable</span>. 
            This is my professional profile—my technical home. Behind the legend is someone extremely private, 
            constantly traveling the globe, building an empire that bridges two worlds most people don't even know exist."
        </div>

        <div class="section" id="story">
            <h2 class="section-title">The Three-Act Journey</h2>
            
            <div class="phase">
                <div class="phase-title">ACT I: Shadow King (2009-2018)</div>
                <p class="timeline-desc">
                    Started at age 8 with BackTrack Linux. By 14, leading red teams in the deep web. 
                    Not playing games—running classified cyber operations. They called me "Untouchable" 
                    in circles where reputation is earned through results, not followers. Top bug hunter. 
                    Red team commander. Gaming legend across Steam, League, CS. This wasn't a career. 
                    This was growing up on the internet at a level most never reach.
                </p>
            </div>

            <div class="phase">
                <div class="phase-title">ACT II: The Constraint (2019-2020)</div>
                <p class="timeline-desc">
                    Forced into law school. Family pressure. COVID hits. Shadow operations go dark. 
                    The most powerful years locked behind institutional walls. But you can cage a hacker's body, 
                    not his mind. During this time, I learned something valuable: legal frameworks, contracts, 
                    compliance—weapons most hackers never have.
                </p>
            </div>

            <div class="phase">
                <div class="phase-title">ACT III: Surface Conquest (2020-2025)</div>
                <p class="timeline-desc">
                    Can't operate in shadows? Conquer the light. Started from zero in legitimate business. 
                    Web design internship → SMMA discovery → SaaS domination. Applied hacker mindset to 
                    business systems. Built AI automation that dominated the entire light industry. 
                    Became top closer in SaaS space. Record-breaking sales. No fake followers. 
                    Just real money from real work. Graduated college 2025 with multiple successful ventures proven.
                </p>
            </div>

            <div class="phase">
                <div class="phase-title">THE CONVERGENCE: Now (2025-Present)</div>
                <p class="timeline-desc">
                    Fresh out of college. Returned to shadow operations with a decade of dormant knowledge 
                    plus 5 years of business mastery. For the first time, not choosing between worlds—
                    operating in both simultaneously. Building what nobody else can: a unified ecosystem 
                    from surface web to dark web. Scaling this architecture into a major company. 
                    The Dragon AI Ecosystem is live and growing.
                </p>
            </div>
        </div>

        <div class="section" id="arsenal">
            <h2 class="section-title">The Arsenal</h2>
            
            <div class="stats-grid">
                <div class="stat-box">
                    <div class="stat-number">10+</div>
                    <div class="stat-label">Years Underground</div>
                </div>
                <div class="stat-box">
                    <div class="stat-number">5+</div>
                    <div class="stat-label">Years Surface Web</div>
                </div>
                <div class="stat-box">
                    <div class="stat-number">2</div>
                    <div class="stat-label">Worlds Mastered</div>
                </div>
                <div class="stat-box">
                    <div class="stat-number pulse">∞</div>
                    <div class="stat-label">Possibilities</div>
                </div>
            </div>

            <div class="timeline">
                <div class="timeline-item">
                    <div class="timeline-year">Shadow Side</div>
                    <div class="timeline-desc">
                        BackTrack/Kali mastery • Deep/Dark web operations • Red team leadership • 
                        Underground bug bounty • Tor/I2P networks • Exploit development • 
                        Zero-day research • OpSec that actually works
                    </div>
                </div>

                <div class="timeline-item">
                    <div class="timeline-year">Light Side</div>
                    <div class="timeline-desc">
                        SaaS sales mastery • SMMA scaling • AI automation architecture • 
                        Law school weapons (contracts, compliance, frameworks) • UI/UX & full-stack dev • 
                        Conversion psychology • High-stakes deals • Enterprise negotiations
                    </div>
                </div>

                <div class="timeline-item">
                    <div class="timeline-year">The Convergence</div>
                    <div class="timeline-desc">
                        AI/AGI with adversarial awareness • Full-spectrum systems (surface to shadow) • 
                        Security-first business architecture • Privacy tools for mainstream • 
                        Underground → Enterprise talent pipelines • Threat intel that drives revenue
                    </div>
                </div>
            </div>
        </div>

        <div class="section" id="dragon">
            <h2 class="section-title">🐉 Dragon AI Ecosystem</h2>
            
            <p style="color: #b0b0b0; line-height: 1.8; margin-bottom: 30px;">
                The unified architecture that bridges two internets. Not theory. Not promises. 
                Live infrastructure operating across all layers—from Fortune 500 boardrooms to Tor hidden services.
            </p>

            <div class="mystery-box" style="border-color: rgba(0, 255, 136, 0.3);">
                <strong style="color: #00ff88;">What makes it different?</strong><br><br>
                Most AI is trained on sanitized surface web data. Dragon AI understands the <em>full spectrum</em>—
                the patterns in shadows and light, the psychology behind public personas and private motivations, 
                the architecture of systems that operate where rules don't exist. This is AGI with street smarts 
                and enterprise polish. Security that thinks like attackers. Business tools with OpSec DNA.
            </div>

            <div style="margin-top: 30px;">
                <div style="color: #00ff88; font-weight: 600; margin-bottom: 15px;">Core Components:</div>
                <div style="color: #b0b0b0; line-height: 2;">
                    ✓ Privacy-first AI with mainstream appeal<br>
                    ✓ Security solutions that think adversarially<br>
                    ✓ Cross-layer automation (surface to shadow)<br>
                    ✓ Enterprise platforms with underground DNA<br>
                    ✓ Red team as a service for Fortune 500s<br>
                    ✓ Talent pipelines: hackers → enterprise security teams
                </div>
            </div>

            <div style="margin-top: 40px; padding: 25px; background: rgba(0, 255, 136, 0.05); border-radius: 10px;">
                <strong style="color: #00ff88;">The Mission:</strong>
                <p style="color: #b0b0b0; margin-top: 10px; line-height: 1.8;">
                    Prove that underground innovation and enterprise success aren't enemies. 
                    Show that offensive security creates business value, not just vulnerability reports. 
                    Build AI that understands the entire internet—not just the parts Google indexes. 
                    Scale this architecture into a company that changes how the world thinks about privacy, 
                    security, and intelligence.
                </p>
            </div>
        </div>

        <div class="section">
            <h2 class="section-title">The Person Behind The Legend</h2>
            
            <p style="color: #b0b0b0; line-height: 1.8; margin-bottom: 20px;">
                I'm extremely private. You won't find me posting daily life updates or chasing social media clout. 
                This profile is my professional persona—where I showcase technical work and connect with serious inquiries.
            </p>

            <div style="margin-top: 25px; padding: 20px; background: rgba(0, 0, 0, 0.3); border-radius: 10px;">
                <div style="color: #888; line-height: 2;">
                    🌍 Traveling the globe constantly<br>
                    ⚽ Playing sports (staying sharp)<br>
                    🎵 Clubbing and nightlife (balance is everything)<br>
                    🎓 Just graduated college<br>
                    🚀 Scaling Dragon AI to enterprise level<br>
                    💼 Multiple successful ventures under my belt
                </div>
            </div>

            <p style="color: #888; margin-top: 25px; font-style: italic;">
                Living life. Building empire. The post-grad grind, just at a different scale.
            </p>
        </div>

        <div class="cta-section" id="contact">
            <h2 class="cta-title">Ready to Connect?</h2>
            <p style="color: #b0b0b0; font-size: 1.1rem; max-width: 700px; margin: 0 auto;">
                For business inquiries, collaborations, consulting, or bookings. 
                I'm selective about what I take on, but if your vision aligns with building 
                the future of the unified internet, let's talk.
            </p>

            <div style="margin: 30px 0; color: #888;">
                <div style="margin: 10px 0;">📧 Business Inquiries: <span class="highlight">[Your Email]</span></div>
                <div style="margin: 10px 0;">💼 LinkedIn: <span class="highlight">[Your Profile]</span></div>
                <div style="margin: 10px 0;">🐦 Twitter/X: <span class="highlight">[Your Handle]</span></div>
                <div style="margin: 10px 0;">📅 Bookings: <span class="highlight">[Your Link]</span></div>
            </div>

            <div style="margin: 30px 0; padding: 20px; background: rgba(0, 255, 136, 0.05); border-radius: 10px;">
                <div style="color: #00ff88; font-weight: 600; margin-bottom: 10px;">Open To:</div>
                <div style="color: #b0b0b0; line-height: 1.8;">
                    Enterprise Security Consulting • AI/AGI Development • SaaS Scaling & Sales Systems • 
                    Strategic Partnerships • Speaking & Technical Workshops • Building the Dragon AI Ecosystem
                </div>
            </div>

            <div class="cta-buttons">
                <a href="mailto:your@email.com" class="cta-button">Get In Touch</a>
                <a href="#" class="cta-button secondary">View Repositories</a>
            </div>

            <div style="margin-top: 40px; color: #666; font-size: 0.9rem;">
                Response time: 24-48 hours for aligned inquiries
            </div>
        </div>

        <div style="text-align: center; margin: 60px 0 40px; color: #666; font-size: 0.95rem; line-height: 1.8;">
            <strong style="color: #00ff88;">From Untouchable to Unstoppable</strong><br>
            Shadow King → Surface Conqueror → Dragon Architect<br><br>
            The legend continues. The ecosystem grows. The internet will never be the same.<br><br>
            <span style="font-size: 0.85rem;">All activities conducted within ethical boundaries and responsible disclosure frameworks.</span>
        </div>
    </div>
</body>
</html>
