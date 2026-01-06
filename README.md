# pico

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pico Robotics | Youth-Led Innovation</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <script src="https://unpkg.com/lucide@latest"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; scroll-behavior: smooth; }
        .glass-card {
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.3);
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-900 selection:bg-blue-100">
    <div id="root"></div>

    <script type="text/babel">
        const { useState, useEffect } = React;

        const Icon = ({ name, className = "w-6 h-6" }) => {
            useEffect(() => {
                if (window.lucide) {
                    window.lucide.createIcons();
                }
            }, [name]);
            return <i data-lucide={name} className={className}></i>;
        };

        const App = () => {
            const services = [
                { title: "Robotics Training", desc: "Beginner to Advanced hands-on education for students.", icon: "graduation-cap" },
                { title: "IoT & Robotics Dev", desc: "Building practical projects for real-world impact.", icon: "cpu" },
                { title: "Institutional Collabs", desc: "Workshops, bootcamps, and STEM club setups.", icon: "users" },
                { title: "National Competitions", desc: "Participation and mentorship for high-level events.", icon: "trophy" },
            ];

            const projects = [
                {
                    id: 'roba',
                    title: "Project ROBA",
                    subtitle: "IoT Telemedicine Robot",
                    achievement: "CHAMPION - National Robotics Championship (NRC)",
                    description: "An IoT-based telemedicine robot designed to assist rural communities and elderly individuals with basic health support and virtual doctor connectivity.",
                    features: [
                        "Bengali & English voice support",
                        "Body temperature measurement",
                        "Heartbeat sensor with OLED display",
                        "Automatic medicine dispensing system",
                        "Symptom/medicine announcement through speaker",
                        "Easy button-based interaction system"
                    ],
                    future: ["ECG sensor implementation", "Blood pressure monitoring", "Online monitoring website"],
                    color: "bg-blue-600",
                    icon: "stethoscope"
                },
                {
                    id: 'road',
                    title: "Smart Road Safety Solution",
                    subtitle: "IoT-Based Prevention System",
                    achievement: "9th Place - 43rd National Science Fest",
                    description: "An intelligent system created to reduce road accidents and improve traffic management through integrated vehicle sensors.",
                    features: [
                        "Vehicle won't start without seatbelt fastened",
                        "Automatic stop if driver falls asleep (Drowsiness detection)",
                        "Doors remain locked until vehicle is safely stopped",
                        "Emergency buttons for police/fire service alerts",
                        "Zone-based automatic speed control",
                        "Auto-stop if obstacles appear suddenly"
                    ],
                    future: [],
                    color: "bg-emerald-600",
                    icon: "car"
                }
            ];

            return (
                <div className="min-h-screen">
                    {/* Navigation */}
                    <nav className="sticky top-0 z-50 bg-white/90 backdrop-blur-md border-b border-slate-200">
                        <div className="max-w-7xl mx-auto px-6 h-20 flex items-center justify-between">
                            <div className="flex items-center gap-2">
                                <div className="bg-blue-600 p-2 rounded-lg text-white">
                                    <Icon name="bot" />
                                </div>
                                <span className="text-xl font-black tracking-tight uppercase">PICO <span className="text-blue-600">ROBOTICS</span></span>
                            </div>
                            <div className="hidden md:flex gap-8 font-semibold text-slate-600">
                                <a href="#about" className="hover:text-blue-600 transition-colors">Who We Are</a>
                                <a href="#projects" className="hover:text-blue-600 transition-colors">Projects</a>
                                <a href="#training" className="hover:text-blue-600 transition-colors">Courses</a>
                                <a href="#contact" className="hover:text-blue-600 transition-colors">Contact</a>
                            </div>
                            <button className="bg-blue-600 text-white px-6 py-2.5 rounded-full font-bold hover:bg-blue-700 transition-all shadow-lg shadow-blue-100">
                                Get Mentorship
                            </button>
                        </div>
                    </nav>

                    {/* Hero Section with Showcase Collage */}
                    <header className="relative pt-20 pb-24 px-6 bg-white overflow-hidden">
                        <div className="absolute top-[-10%] left-[-10%] w-[40%] h-[40%] bg-blue-50 rounded-full blur-[120px] opacity-60"></div>
                        <div className="max-w-7xl mx-auto grid lg:grid-cols-2 gap-16 items-center relative">
                            <div className="text-center lg:text-left">
                                <div className="inline-flex items-center gap-2 bg-blue-50 text-blue-700 px-4 py-2 rounded-full text-xs font-black tracking-widest mb-6 border border-blue-100 uppercase">
                                    <Icon name="zap" className="w-4 h-4" /> Youth-Led STEM Initiative
                                </div>
                                <h1 className="text-5xl lg:text-7xl font-black leading-[1.1] mb-8 text-slate-900">
                                    Empowering <span className="text-blue-600">Innovation</span> Through Robotics.
                                </h1>
                                <p className="text-xl text-slate-600 mb-10 leading-relaxed max-w-xl mx-auto lg:mx-0 font-medium">
                                    Pico Robotics is a youth-led initiative from Bangladesh, focused on making robotics accessible, affordable, and impactful for students and communities.
                                </p>
                                <div className="flex flex-col sm:flex-row items-center justify-center lg:justify-start gap-4">
                                    <a href="#projects" className="w-full sm:w-auto bg-slate-900 text-white px-10 py-4 rounded-2xl font-bold hover:bg-slate-800 transition-all flex items-center justify-center gap-2 shadow-xl shadow-slate-200">
                                        View Our Impact <Icon name="arrow-right" className="w-5 h-5" />
                                    </a>
                                    <a href="#training" className="w-full sm:w-auto bg-white border border-slate-200 text-slate-700 px-10 py-4 rounded-2xl font-bold hover:bg-slate-50 transition-all text-center">
                                        Our Programs
                                    </a>
                                </div>
                            </div>

                            <div className="relative group">
                                <div className="absolute -inset-4 bg-gradient-to-r from-blue-500/20 to-purple-500/20 rounded-[4rem] blur-3xl opacity-50 group-hover:opacity-100 transition-opacity duration-500"></div>
                                <div className="aspect-[4/5] md:aspect-square bg-slate-100/50 rounded-[4rem] border border-white shadow-2xl relative overflow-hidden flex items-center justify-center p-4">
                                    <div className="relative w-full h-full flex items-center justify-center">
                                        {/* Project ROBA Card Overlay */}
                                        <div className="absolute z-20 w-[85%] bg-white rounded-3xl shadow-2xl p-6 transform -rotate-2 hover:rotate-0 transition-all duration-500 border border-slate-100">
                                            <div className="flex items-center justify-between mb-4">
                                                <div className="flex items-center gap-3">
                                                    <div className="w-10 h-10 bg-blue-600 rounded-xl flex items-center justify-center text-white">
                                                        <Icon name="stethoscope" className="w-5 h-5" />
                                                    </div>
                                                    <div>
                                                        <div className="text-sm font-black text-slate-900">Project ROBA</div>
                                                        <div className="text-[10px] font-bold text-slate-400 uppercase tracking-widest">Telemedicine Robot</div>
                                                    </div>
                                                </div>
                                                <div className="bg-yellow-400 text-slate-900 text-[10px] font-black px-3 py-1 rounded-full uppercase tracking-tighter shadow-sm">
                                                    Champion (NRC)
                                                </div>
                                            </div>
                                            <div className="space-y-3">
                                                <div className="flex items-center justify-between text-[11px] font-bold text-slate-600 bg-slate-50 p-2.5 rounded-xl border border-slate-100">
                                                    <span>Bengali Voice Support</span>
                                                    <Icon name="shield-check" className="w-4 h-4 text-emerald-500" />
                                                </div>
                                                <div className="flex items-center justify-between text-[11px] font-bold text-slate-600 bg-slate-50 p-2.5 rounded-xl border border-slate-100">
                                                    <span>Automatic Medicine Dispenser</span>
                                                    <Icon name="shield-check" className="w-4 h-4 text-emerald-500" />
                                                </div>
                                            </div>
                                        </div>

                                        {/* Academy Card Overlay */}
                                        <div className="absolute z-10 bottom-4 right-4 w-[65%] bg-slate-900 rounded-[2.5rem] p-6 shadow-2xl transform rotate-6 hover:rotate-2 transition-all duration-500 border border-slate-800">
                                            <div className="flex items-center gap-3 mb-4">
                                                <Icon name="graduation-cap" className="text-blue-400 w-8 h-8" />
                                                <div>
                                                    <div className="text-white text-xs font-black">Robotics Academy</div>
                                                    <div className="text-[9px] text-slate-500 font-bold uppercase tracking-widest leading-none">Basic to Advanced</div>
                                                </div>
                                            </div>
                                            <div className="grid grid-cols-2 gap-2 mb-2">
                                                <div className="bg-white/5 p-2 rounded-xl text-center">
                                                    <div className="text-[8px] text-slate-500 font-bold mb-1">C++ / Arduino</div>
                                                </div>
                                                <div className="bg-white/5 p-2 rounded-xl text-center">
                                                    <div className="text-[8px] text-slate-500 font-bold mb-1">Circuit Design</div>
                                                </div>
                                            </div>
                                        </div>
                                        
                                        {/* Floating Achievement Badge */}
                                        <div className="absolute top-1/4 -left-4 z-30 bg-white shadow-xl rounded-2xl p-4 border border-slate-50 flex flex-col items-center gap-1 scale-90 md:scale-100">
                                            <Icon name="trophy" className="text-yellow-500 w-6 h-6" />
                                            <div className="text-lg font-black leading-none">#1</div>
                                            <div className="text-[8px] font-bold text-slate-400 uppercase tracking-widest">National</div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </header>

                    {/* What We Do Services */}
                    <section id="about" className="py-24 px-6 max-w-7xl mx-auto">
                        <div className="flex flex-col md:flex-row md:items-end justify-between mb-16 gap-6">
                            <div className="max-w-2xl">
                                <h2 className="text-3xl font-black mb-4 uppercase tracking-tight text-blue-600">What We Do</h2>
                                <p className="text-xl text-slate-500 font-medium leading-relaxed">From hands-on beginner training to high-impact IoT solutions, we build practical technology for the community.</p>
                            </div>
                            <div className="hidden md:block h-px flex-grow mx-12 bg-slate-200"></div>
                        </div>
                        <div className="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
                            {services.map((s, i) => (
                                <div key={i} className="group bg-white p-8 rounded-[2rem] border border-slate-100 shadow-sm hover:shadow-2xl hover:-translate-y-2 transition-all duration-300">
                                    <div className="bg-blue-50 w-16 h-16 rounded-2xl flex items-center justify-center text-blue-600 mb-8 group-hover:bg-blue-600 group-hover:text-white transition-colors duration-300">
                                        <Icon name={s.icon} className="w-8 h-8" />
                                    </div>
                                    <h3 className="font-black text-xl mb-3">{s.title}</h3>
                                    <p className="text-slate-500 text-sm leading-relaxed">{s.desc}</p>
                                </div>
                            ))}
                        </div>
                    </section>

                    {/* Flagship Projects Detail */}
                    <section id="projects" className="py-24 px-6 bg-slate-900 text-white rounded-[3.5rem] mx-4 my-8 overflow-hidden relative">
                        <div className="absolute top-0 right-0 w-96 h-96 bg-blue-500/10 rounded-full blur-[100px]"></div>
                        <div className="max-w-7xl mx-auto relative">
                            <div className="text-center mb-20">
                                <h2 className="text-4xl md:text-5xl font-black mb-6 tracking-tight">Flagship Innovations</h2>
                                <p className="text-slate-400 max-w-2xl mx-auto text-lg font-medium">Award-winning solutions that tackle real-world challenges in health and safety.</p>
                            </div>
                            <div className="grid lg:grid-cols-2 gap-12">
                                {projects.map((project) => (
                                    <div key={project.id} className="flex flex-col bg-white/5 rounded-[2.5rem] border border-white/10 hover:border-blue-500/30 transition-all p-8 md:p-12">
                                        <div className="flex flex-wrap justify-between items-start gap-4 mb-10">
                                            <div className={`${project.color} w-20 h-20 rounded-3xl flex items-center justify-center shadow-2xl text-white`}>
                                                <Icon name={project.icon} className="w-10 h-10" />
                                            </div>
                                            <div className="flex flex-col items-end">
                                                <div className="inline-flex items-center gap-2 bg-yellow-400/10 text-yellow-400 px-4 py-1.5 rounded-full text-[10px] font-black tracking-widest border border-yellow-400/20 mb-2 uppercase">
                                                    <Icon name="award" className="w-3 h-3" /> {project.achievement.split(' - ')[0]}
                                                </div>
                                                <div className="text-[10px] text-slate-500 font-bold uppercase tracking-widest">{project.achievement.split(' - ')[1]}</div>
                                            </div>
                                        </div>
                                        <h3 className="text-3xl font-black mb-2">{project.title}</h3>
                                        <div className="text-blue-400 font-bold uppercase tracking-widest text-sm mb-6">{project.subtitle}</div>
                                        <p className="text-slate-400 mb-8 text-lg leading-relaxed">{project.description}</p>
                                        <div className="space-y-6 mb-10 flex-grow">
                                            <div className="text-xs font-black text-slate-500 uppercase tracking-widest mb-4">Core Features</div>
                                            <div className="grid md:grid-cols-2 gap-4">
                                                {project.features.map((feature, i) => (
                                                    <div key={i} className="flex items-start gap-3 text-sm text-slate-300 font-medium">
                                                        <div className="mt-1 w-4 h-4 rounded-full bg-blue-500/20 flex items-center justify-center flex-shrink-0">
                                                            <div className="w-1.5 h-1.5 bg-blue-400 rounded-full"></div>
                                                        </div>
                                                        {feature}
                                                    </div>
                                                ))}
                                            </div>
                                        </div>
                                        {project.future.length > 0 && (
                                            <div className="pt-8 border-t border-white/10">
                                                <div className="text-xs font-black text-slate-500 uppercase tracking-widest mb-4">Future Goals</div>
                                                <div className="flex flex-wrap gap-2">
                                                    {project.future.map((f, i) => (
                                                        <span key={i} className="px-3 py-1 bg-white/5 rounded-lg text-xs text-blue-300 border border-white/5">{f}</span>
                                                    ))}
                                                </div>
                                            </div>
                                        )}
                                    </div>
                                ))}
                            </div>
                        </div>
                    </section>

                    {/* Academy & Instructor Section */}
                    <section id="training" className="py-24 px-6 max-w-7xl mx-auto">
                        <div className="bg-white rounded-[3rem] border border-slate-100 shadow-xl overflow-hidden grid lg:grid-cols-5">
                            <div className="lg:col-span-3 p-8 md:p-16">
                                <h2 className="text-4xl font-black mb-8 text-slate-900 tracking-tight">Academic Programs</h2>
                                <div className="space-y-12">
                                    <div className="relative pl-8 border-l-4 border-blue-600">
                                        <div className="absolute -left-3.5 top-0 w-6 h-6 bg-blue-600 rounded-full flex items-center justify-center text-white text-[10px] font-bold">1</div>
                                        <h3 className="text-xl font-black mb-2 text-slate-800">Basic to Advanced Robotics Course (Bangla)</h3>
                                        <div className="flex flex-wrap gap-4 mb-6 text-sm">
                                            <span className="bg-slate-100 text-slate-600 px-3 py-1 rounded-full font-bold">Bangla Medium</span>
                                            <span className="bg-blue-50 text-blue-600 px-3 py-1 rounded-full font-bold">Professional Certificate</span>
                                        </div>
                                        <div className="grid sm:grid-cols-2 gap-x-8 gap-y-3 mb-8">
                                            {["Microcontrollers", "Circuit Design", "Sensors", "C++ Programming", "Robot Development"].map((topic, i) => (
                                                <div key={i} className="flex items-center gap-2 text-slate-600 font-semibold text-sm">
                                                    <Icon name="chevron-right" className="w-4 h-4 text-blue-600" /> {topic}
                                                </div>
                                            ))}
                                        </div>
                                        <div className="p-5 bg-slate-50 rounded-2xl flex items-center gap-4 border border-slate-100">
                                            <div className="w-12 h-12 bg-white rounded-xl shadow-sm flex items-center justify-center text-blue-600"><Icon name="users" /></div>
                                            <div>
                                                <div className="text-[10px] text-slate-400 font-bold uppercase tracking-widest">Lead Instructor</div>
                                                <div className="font-black text-slate-800 text-sm uppercase">M. Shoyab Sadik <span className="text-slate-400 font-medium lowercase">BSc in EEE, IUBAT</span></div>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                            <div className="lg:col-span-2 bg-blue-600 p-8 md:p-16 text-white flex flex-col justify-center">
                                <h3 className="text-3xl font-black mb-10 leading-tight">Why Collaborate With Us?</h3>
                                <ul className="space-y-8">
                                    {["National-level achievements", "Practical, real-world solutions", "Scalable workshops & capacity", "Social impact focused innovation"].map((item, i) => (
                                        <li key={i} className="flex items-start gap-4 font-bold text-lg leading-snug">
                                            <Icon name="shield-check" className="w-6 h-6 flex-shrink-0 mt-0.5" /> {item}
                                        </li>
                                    ))}
                                </ul>
                                <div className="mt-16 pt-10 border-t border-white/20">
                                    <p className="text-lg italic font-medium opacity-90 leading-relaxed">"To build a future where young innovators lead Bangladesh in robotics, automation, and real-world problem-solving."</p>
                                </div>
                            </div>
                        </div>
                    </section>

                    {/* Footer Contact */}
                    <footer id="contact" className="bg-white border-t border-slate-200 py-20 px-6">
                        <div className="max-w-7xl mx-auto flex flex-col md:flex-row justify-between items-start gap-12">
                            <div className="max-w-sm">
                                <div className="flex items-center gap-2 mb-6">
                                    <div className="bg-blue-600 p-2 rounded-lg text-white">
                                        <Icon name="bot" />
                                    </div>
                                    <span className="text-2xl font-black tracking-tight uppercase">PICO ROBOTICS</span>
                                </div>
                                <p className="text-slate-500 font-medium mb-8 leading-relaxed">Empowering the youth of Bangladesh through hands-on STEM education and accessible robotics technology.</p>
                                <div className="flex gap-4">
                                    <a href="#" className="w-12 h-12 bg-slate-100 rounded-2xl flex items-center justify-center text-slate-600 hover:bg-blue-600 hover:text-white transition-all"><Icon name="facebook" /></a>
                                    <a href="mailto:picorobotics@gmail.com" className="w-12 h-12 bg-slate-100 rounded-2xl flex items-center justify-center text-slate-600 hover:bg-blue-600 hover:text-white transition-all"><Icon name="mail" /></a>
                                </div>
                            </div>
                            <div className="space-y-8">
                                <h4 className="text-xs font-black uppercase tracking-[0.2em] text-slate-400">Contact Details</h4>
                                <div className="space-y-4">
                                    <div className="flex items-center gap-4 text-slate-700 font-bold">
                                        <Icon name="mail" className="text-blue-600" /> picorobotics@gmail.com
                                    </div>
                                    <div className="flex items-center gap-4 text-slate-700 font-bold">
                                        <Icon name="map-pin" className="text-blue-600" /> Dhaka, Bangladesh
                                    </div>
                                    <div className="flex items-center gap-4 text-slate-700 font-bold">
                                        <Icon name="facebook" className="text-blue-600" /> Pico Robotics
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div className="max-w-7xl mx-auto mt-20 pt-8 border-t border-slate-100 text-slate-400 text-xs font-bold uppercase tracking-widest flex justify-between">
                            <span>© {new Date().getFullYear()} Pico Robotics Bangladesh</span>
                            <span>STEM Excellence</span>
                        </div>
                    </footer>
                </div>
            );
        };

        const root = ReactDOM.createRoot(document.getElementById('root'));
        root.render(<App />);
    </script>
</body>
</html>
