# orientation-anton
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Orientation Anton 2026</title>
    <!-- Chargement de Tailwind CSS pour le style -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Chargement de React, ReactDOM et Babel pour transformer le code en direct -->
    <script src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <!-- Icônes Lucides -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;700;900&display=swap');
        corps { police-family: 'Inter', sans-serif; }
    </style>
</head>
<body class="bg-slate-950">
    <div id="root"></div>

    <script type="text/babel">
        // Importation manuelle des icônes Lucide pour la version HTML
        const {
            Processeur, ShieldCheck, Base de données, Manette de jeu 2, Horloge, Chapeau de remise de diplôme,
            Cible, Triangle d'alerte, Chevron gauche, Flèche droite, Vélo,
            Clé, Livre, CheckCircle2, TrendingUp, FileText, Copier,
            Épingle de carte, Ampoule, Calques
        } = {
            Processeur : (propriétés) => <i data-lucide="cpu" {...propriétés}></i>,
            ShieldCheck: (props) => <i data-lucide="shield-check" {...props}></i>,
            Base de données : (props) => <i data-lucide="database" {...props}></i>,
            Gamepad2: (props) => <i data-lucide="gamepad-2" {...props}></i>,
            Horloge : (props) => <i data-lucide="clock" {...props}></i>,
            GraduationCap: (props) => <i data-lucide="graduation-cap" {...props}></i>,
            Cible : (props) => <i data-lucide="target" {...props}></i>,
            AlertTriangle : (props) => <i data-lucide="alert-triangle" {...props}></i>,
            ChevronLeft: (props) => <i data-lucide="chevron-left" {...props}></i>,
            ArrowRight: (props) => <i data-lucide="arrow-right" {...props}></i>,
            Vélo : (accessoires) => <i data-lucide="vélo" {...accessoires}></i>,
            Clé à molette : (propriétés) => <i data-lucide="clé à molette" {...propriétés}></i>,
            Livre : (accessoires) => <i data-lucide="livre" {...accessoires}></i>,
            CheckCircle2: (props) => <i data-lucide="check-circle-2" {...props}></i>,
            Tendance à la hausse : (propriétés) => <i data-lucide="trending-up" {...propriétés}></i>,
            FileText: (props) => <i data-lucide="file-text" {...props}></i>,
            Copie : (props) => <i data-lucide="copy" {...props}></i>,
            MapPin: (props) => <i data-lucide="map-pin" {...props}></i>,
            Ampoule : (props) => <i data-lucide="ampoule" {...props}></i>,
            Calques : (props) => <i data-lucide="layers" {...props}></i>
        };

        const App = () => {
            const [selectedJob, setSelectedJob] = React.useState(null);
            const [copié, setCopied] = React.useState(false);

            React.useEffect(() => {
                // Initialisation des icônes après le rendu
                si (window.lucide) window.lucide.createIcons();
            }, [emploi sélectionné]);

            const handleCopy = (texte) => {
                const textArea = document.createElement("textarea");
                textArea.value = texte;
                document.body.appendChild(textArea);
                textArea.select();
                document.execCommand('copie');
                définirCopie(vrai);
                setTimeout(() => setCopied(false), 2000);
                document.body.removeChild(textArea);
            };

            const emplois = [
                {
                    id : "embarquement",
                    titre : "Architecte Systèmes Embarqués",
                    Titre court : "Électronique & Code",
                    icône : <Cpu className="w-8 h-8" />,
                    couleur : « bleu »,
                    description: "Le métier qui fait le pont entre le logiciel et le matériel physique. C'est l'intelligence des objets : voitures, drones, ou vélos électriques.",
                    quotidiennement : "Programmer des processeurs pour qu'ils gèrent de l'énergie, des moteurs ou des capteurs.",
                    WhyAnton: "C'est la suite logique de son projet de SI (vélo électrique). Son côté 'touche-à-tout' technique est un atout majeur.",
                    points forts : ["Lien Hardware/Software", "Esprit de diagnostic", "Maths & SI appliquées"],
                    pathInitial: "École d'ingénieurs post-bac (Polytech, INSA) ou BUT GEII (Valence/Lyon).",
                    parcoursAlternance: "Apprentissage très fréquent en fin de cycle ingénieur.",
                    tags : ["Mobilité", "Matériel", "Robotique"],
                    Lettre de motivation : "Passionné par l'informatique appliquée au matériel, je consacre mon temps libre à la réparation de PC et à la conception technique. Actuellement en Terminale avec les spécialités Mathématiques et Sciences de l'Ingénieur, je développe un projet de motorisation électrique pour un vélo. Cette expérience m'a appris à gérer des contraintes réelles de puissance et de programmation. Mon approche est directe : je privilégie l'efficacité de la solution. Je souhaite intégrer votre formation pour approfondir mes compétences en systèmes embarqués."
                },
                {
                    id : "cyber",
                    titre : "Expert en Cybersécurité",
                    titre court : "Gardien des Systèmes",
                    icône : <ShieldCheck className="w-8 h-8" />,
                    couleur : « rouge »,
                    description: "Analyser, protéger et tester la résistance des systèmes informatiques face aux menaces.",
                    quotidiennement : "Rechercher des vulnérabilités, configurer des protections et auditer des codes.",
                    WhyAnton: "Son option Latin et son goût pour les règles de JDR montrer une structure mentale idéale.",
                    points forts : ["Rigueur logique", "Calme et discrétion", "Capacité d'analyse"],
                    pathInitial: "Idéal pour obtenir un socle théorique solide en mathématiques et cryptographie.",
                    parcoursAlternance: "Très recherché dès le Bac+3 (Bachelor ou BUT).",
                    tags : ["Défense", "Logique", "Données"],
                    Lettre de motivation : "Mon parcours scientifique, enrichi par une option Latin, m'a donné le goût des structures logiques complexes. Je souhaite orienter mes études vers la cybersécurité pour apprendre à protéger les infrastructures numériques. Ma pratique des jeux de rôle m'a habitué à analyser des systèmes de règles et à identifier leurs points de rupture. Mon tempérament calme et ma capacité à aller droit au mais sont des atouts que je souhaite mettre au service de la sécurisation des données."
                },
                {
                    id : "devops",
                    titre : "Ingénieur DevOps / Cloud",
                    Titre court : « Architecte Infrastructure »,
                    icône : <Database className="w-8 h-8" />,
                    couleur : « émeraude »,
                    description: "L'architecte qui construit et automatise les systèmes pour que les applications fonctionnent partout sans interruption.",
                    quotidiennement : "Coder des scripts pour automatiser des serveurs et optimiser les performances.",
                    WhyAnton : "Il aime démonter les PC. Le DevOps, c'est démonter et remonter des usines numériques entières.",
                    points forts : ["Efficacité (résultat)", "Sens du système", "Fiabilité"],
                    pathInitial: "Bonne option pour maîtriser les concepts de réseau et virtualisation.",
                    pathAlternance: "Métier qui s'apprend beaucoup par la pratique terrain.",
                    tags: ["Cloud", "Système", "Efficacité"],
                    Lettre de motivation : "Mon intérêt pour l'informatique a débuté par la réparation matérielle de machines. Aujourd'hui, je souhaite transposer cette compréhension du hardware vers l'architecture de systèmes cloud. Élève constante avec 13 de moyenne, je possède la persévérance nécessaire pour gérer des infrastructures complexes. Ma méthode repose sur le pragmatisme : identifier la solution la plus directe pour stabiliser un système."
                },
                {
                    id : "jeu",
                    titre : "Game Designer / Moteur",
                    Titre court : "Architecte de Mondes",
                    icône : <Gamepad2 className="w-8 h-8" />,
                    couleur : « violet »,
                    description: "Créer les lois mathématiques et physiques d'un monde virtuel. Équilibrer les mécaniques de jeu.",
                    quotidien : "Transformer des idées en algorithmes. Équilibrer des statistiques, coder la physique.",
                    WhyAnton: "Il retravaille déjà les règles de ses JDR. C'est du Game Design systémique.",
                    points forts : ["Créativité structurée", "Maths Expertes", "Sens du système"],
                    pathInitial: "Préférable pour se constituer un portfolio et participer à des Game Jams.",
                    pathAlternance: "Plus rare, souvent en fin de Master.",
                    tags : ["Création", "Maths", "JDR"],
                    Lettre de motivation : "Depuis plusieurs années, je conçois des systèmes de règles pour mes jeux de rôle. Je souhaite mettre cette passion et ma rigueur scientifique au service du Game Design. Mon objectif n'est pas seulement de consommer du jeu vidéo, mais d'en construire le moteur logique. Mon profil constant et réfléchi me permet d'aborder des projets de conception ambitieux avec la patience et la logique nécessaire."
                }
            ];

            si (emploi sélectionné) {
                retour (
                    <div className="min-h-screen bg-slate-950 text-slate-100 p-4 md:p-8">
                        <button onClick={() => setSelectedJob(null)} className="flex items-center gap-2 text-slate-400 hover:text-white mb-8 transition-colors">
                            <ChevronLeft /> Retour au Tableau de bord
                        </button>
                        <div className="max-w-5xl mx-auto">
                            <div className="flex flex-col md:flex-row gap-8 items-start mb-12">
                                <div className={`p-6 rounded-3xl bg-slate-800 border border-slate-700 shadow-xl`}>
                                    {icôneJobSélectionné}
                                </div>
                                <div className="flex-1">
                                    <h1 className="text-4xl font-extrabold mb-4">{selectedJob.title}</h1>
                                    <p className="text-xl text-slate-400 leading-relaxed">{selectedJob.description}</p>
                                </div>
                            </div>
                            <div className="grid lg:grid-cols-3 gap-6">
                                <div className="lg:col-span-2 espace-y-6">
                                    <div className="bg-slate-900 border border-slate-800 rounded-3xl p-8 shadow-lg">
                                        <h3 className="text-lg font-bold mb-6 flex items-center gap-2 text-blue-400"><FileText /> Lettre de Motivation (Base)</h3>
                                        <div className="bg-slate-950 rounded-2xl p-6 border border-slate-800 text-slate-300 text-sm md:text-base">
                                            <p>{selectedJob.motivationLetter}</p>
                                            <button onClick={() => handleCopy(selectedJob.motivationLetter)} className="mt-4 px-4 py-2 bg-slate-800 rounded-lg text-xs font-bold">
                                                {copié ? "Copié !" : "Copieur"}
                                            </button>
                                        </div>
                                    </div>
                                    <div className="bg-slate-900 border border-slate-800 rounded-3xl p-8">
                                        <h3 className="text-lg font-bold mb-6 flex items-center gap-2 text-blue-400"><Formations d'ampoules/></h3>
                                        <div className="grid md:grid-cols-2 gap-4">
                                            <div className="bg-slate-800 p-5 rounded-2xl border border-blue-500/20">
                                                <h4 className="font-bold text-blue-400 mb-2 text-xs uppercase">Initiale</h4>
                                                <p className="text-xs text-slate-300">{selectedJob.pathInitial}</p>
                                            </div>
                                            <div className="bg-slate-800 p-5 rounded-2xl border border-emerald-500/20">
                                                <h4 className="font-bold text-emerald-400 mb-2 text-xs uppercase">Alternance</h4>
                                                <p className="text-xs text-slate-300">{selectedJob.pathAlternance}</p>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                                <div className="space-y-6">
                                    <div className="bg-blue-600 rounded-3xl p-6 shadow-xl">
                                        <h3 className="text-white font-bold mb-2 uppercase text-xs">Le Quotidien</h3>
                                        <p className="text-blue-100 text-sm italic">{selectedJob.daily}</p>
                                    </div>
                                    <div className="bg-slate-900 border border-slate-800 rounded-3xl p-6">
                                        <h3 className="text-slate-400 font-bold mb-2 uppercase text-xs">À tous Anton</h3>
                                        <ul className="space-y-2">
                                            {selectedJob.strengths.map((s, i) => (
                                                <li key={i} className="flex items-center gap-2 text-xs text-slate-300">
                                                    <CheckCircle2 className="w-3 h-3 text-emerald-500" /> {s}
                                                </li>
                                            ))}
                                        </ul>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                );
            }

            retour (
                <div className="min-h-screen p-4 md:p-8">
                    <div className="max-w-6xl mx-auto">
                        <header className="mb-12">
                            <h1 className="text-5xl font-black text-white uppercase tracking-tighter">Anton <span className="text-blue-500">2026</span></h1>
                            <p className="text-slate-500 mt-2 font-bold tracking-widest uppercase text-sm">Drôme • Lyon • Orientation</p>
                            <div className="h-1 w-32 bg-blue-500 mt-4"></div>
                        </header>
                        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 mb-12">
                            {jobs.map((job) => (
                                <button key={job.id} onClick={() => setSelectedJob(job)} className="bg-slate-900 border border-slate-800 rounded-3xl p-6 text-left hover:border-blue-500 transition-all group">
                                    <div className="mb-6 text-slate-400 group-hover:text-blue-400">{job.icon}</div>
                                    <h3 className="text-white font-bold mb-2 group-hover:text-blue-400 transition-colors">{job.title}</h3>
                                    <p className="text-xs text-slate-500">{job.shortTitle}</p>
                                </button>
                            ))}
                        </div>
                        <div className="grid md:grid-cols-2 gap-6">
                            <div className="bg-slate-900 border border-slate-800 rounded-3xl p-8">
                                <h3 className="text-white font-bold mb-4 flex items-center gap-2"><Target className="text-blue-500" /> Analyse</h3>
                                <div className="space-y-4">
                                    <p className="text-sm text-slate-400"><span className="text-white font-bold">Math Exp / SI / Latin :</span> Un profil structuré et rare, idéal pour les écoles d'ingénieurs.</p>
                                    <p className="text-sm text-slate-400"><span className="text-white font-bold">Projet Vélo :</span> L'argument majeur pour prouver son autonomie technique.</p>
                                </div>
                            </div>
                            <div className="bg-blue-600 rounded-3xl p-8 flex flex-col justify-center">
                                <p className="text-white font-bold italic leader-relaxed text-lg">"Le 13 de moyenne constante est un gage de fiabilité totale pour les recruteurs."</p>
                            </div>
                        </div>
                    </div>
                </div>
            );
        };

        const root = ReactDOM.createRoot(document.getElementById('root'));
        racine.render(<App />);
    </script>
</body>
</html>
