# simulateur-cout-assistante
Comparez les coûts d'une Assistante Administrative Salarié / Indépendante
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simulateur Coût Assistante Administrative - Indépendante vs Salariée</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            box-sizing: border-box;
        }
        
        .gradient-bg {
            background: linear-gradient(135deg, #7c3aed 0%, #a855f7 30%, #c084fc 70%, #d8b4fe 100%);
        }
        
        .glass-effect {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        .comparison-card {
            transition: all 0.3s ease;
        }
        
        .comparison-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
        }
        
        .savings-highlight {
            background: linear-gradient(45deg, #10b981 0%, #059669 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .cost-highlight {
            background: linear-gradient(45deg, #ef4444 0%, #dc2626 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        input[type="range"] {
            -webkit-appearance: none;
            appearance: none;
            background: transparent;
            cursor: pointer;
        }
        
        input[type="range"]::-webkit-slider-track {
            background: #e2e8f0;
            height: 6px;
            border-radius: 3px;
        }
        
        input[type="range"]::-webkit-slider-thumb {
            -webkit-appearance: none;
            appearance: none;
            background: linear-gradient(135deg, #a855f7, #c084fc);
            height: 20px;
            width: 20px;
            border-radius: 50%;
            cursor: pointer;
        }
        
        .animate-fade-in {
            animation: fadeIn 0.5s ease-in;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .benefit-icon {
            font-size: 2rem;
            margin-bottom: 0.5rem;
        }
        
        .brand-gradient {
            background: linear-gradient(135deg, #7c3aed 0%, #a855f7 40%, #c084fc 80%, #d8b4fe 100%);
        }
    </style>
</head>
<body class="gradient-bg min-h-screen py-8 px-4">
    <div class="max-w-7xl mx-auto">
        <!-- Header -->
        <div class="text-center mb-12 animate-fade-in">
            <!-- Profile Section -->
            <div class="flex flex-col md:flex-row items-center justify-center gap-8 mb-8">
                <div class="relative">
                    <div class="w-32 h-32 bg-white rounded-full flex items-center justify-center shadow-xl overflow-hidden">
                        <img src="https://sylvie-chaussadas.fr/wp-content/uploads/2025/04/Photo-profil-IN-FG.png" 
                             alt="Sylvie CHAUSSADAS - SChau-MY" 
                             class="w-28 h-28 rounded-full object-cover"
                             onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="w-28 h-28 brand-gradient rounded-full flex items-center justify-center text-white text-2xl font-bold shadow-lg" style="display: none;">
                            <div class="text-center">
                                <div class="text-3xl font-extrabold">SC</div>
                                <div class="text-xs font-medium -mt-1">hau-MY</div>
                            </div>
                        </div>
                    </div>
                    <div class="absolute -bottom-2 -right-2 bg-green-500 text-white px-3 py-1 rounded-full text-xs font-bold">
                        Disponible
                    </div>
                </div>
                <div class="text-center md:text-left">
                    <div class="bg-white/20 backdrop-blur-sm rounded-2xl p-6 mb-4">
                        <h2 class="text-2xl font-bold text-white mb-2">SChau-MY</h2>
                        <p class="text-xl text-white/90 font-semibold">Sylvie CHAUSSADAS</p>
                        <p class="text-white/80">Assistante Administrative Indépendante</p>
                    </div>
                    <div class="flex flex-wrap justify-center md:justify-start gap-2">
                        <a href="tel:0628900114" class="bg-white/20 backdrop-blur-sm text-white px-3 py-2 rounded-lg hover:bg-white/30 transition-all flex items-center gap-2 text-sm">
                            📞 06 28 90 01 14
                        </a>
                        <a href="mailto:contact@sylvie-chaussadas.fr" class="bg-white/20 backdrop-blur-sm text-white px-3 py-2 rounded-lg hover:bg-white/30 transition-all flex items-center gap-2 text-sm">
                            ✉️ Contact
                        </a>
                        <a href="https://sylvie-chaussadas.fr/" target="_blank" rel="noopener noreferrer" class="bg-white/20 backdrop-blur-sm text-white px-3 py-2 rounded-lg hover:bg-white/30 transition-all flex items-center gap-2 text-sm">
                            🌐 Site Web
                        </a>
                        <a href="https://www.linkedin.com/in/sylvie-chaussadas/" target="_blank" rel="noopener noreferrer" class="bg-white/20 backdrop-blur-sm text-white px-3 py-2 rounded-lg hover:bg-white/30 transition-all flex items-center gap-2 text-sm">
                            💼 LinkedIn
                        </a>
                        <a href="https://calendly.com/sylviechaussadas/reservez_votre_appel_decouverte_maintenant" target="_blank" rel="noopener noreferrer" class="bg-violet-500/80 backdrop-blur-sm text-white px-3 py-2 rounded-lg hover:bg-violet-600/80 transition-all flex items-center gap-2 text-sm font-semibold">
                            📅 RDV Gratuit
                        </a>
                    </div>
                </div>
            </div>
            
            <h1 class="text-4xl md:text-5xl font-bold text-white mb-4">
                💼 Simulateur Coût Réel
            </h1>
            <p class="text-xl text-white/80 mb-2">Indépendante vs Salariée</p>
            <p class="text-white/60">Découvrez les économies réelles pour votre TPE/PME</p>
        </div>

        <!-- Configuration Panel -->
        <div class="glass-effect rounded-3xl p-8 mb-8 animate-fade-in">
            <h2 class="text-2xl font-bold text-white mb-6 text-center">⚙️ Configuration de votre besoin</h2>
            
            <div class="grid md:grid-cols-3 gap-6 mb-6">
                <div class="bg-white rounded-2xl p-6">
                    <h3 class="text-lg font-bold text-gray-800 mb-4">📊 Volume de travail</h3>
                    <div class="space-y-4">
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">
                                Heures par semaine: <span id="hours-display">20</span>h
                            </label>
                            <input type="range" id="hours-slider" min="5" max="35" value="20" 
                                   class="w-full" onchange="updateCalculation()">
                        </div>
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">
                                Semaines par an: <span id="weeks-display">48</span>
                            </label>
                            <input type="range" id="weeks-slider" min="40" max="52" value="48" 
                                   class="w-full" onchange="updateCalculation()">
                        </div>
                    </div>
                </div>

                <div class="bg-white rounded-2xl p-6">
                    <h3 class="text-lg font-bold text-gray-800 mb-4">💰 Tarification</h3>
                    <div class="space-y-4">
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">
                                Tarif indépendante: <span id="rate-display">35</span>€/h
                            </label>
                            <input type="range" id="rate-slider" min="25" max="50" value="35" 
                                   class="w-full" onchange="updateCalculation()">
                        </div>
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">
                                Salaire brut souhaité: <span id="salary-display">2200</span>€/mois
                            </label>
                            <input type="range" id="salary-slider" min="1800" max="3000" value="2200" step="100"
                                   class="w-full" onchange="updateCalculation()">
                        </div>
                    </div>
                </div>

                <div class="bg-white rounded-2xl p-6">
                    <h3 class="text-lg font-bold text-gray-800 mb-4">🏢 Votre entreprise</h3>
                    <div class="space-y-4">
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">Taille entreprise</label>
                            <select id="company-size" class="w-full p-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-violet-500" onchange="updateCalculation()">
                                <option value="tpe">TPE (< 10 salariés)</option>
                                <option value="pe">PE (10-49 salariés)</option>
                                <option value="me">ME (50-249 salariés)</option>
                            </select>
                        </div>
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">Secteur d'activité</label>
                            <select id="sector" class="w-full p-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-violet-500" onchange="updateCalculation()">
                                <option value="service">Services</option>
                                <option value="commerce">Commerce</option>
                                <option value="industrie">Industrie</option>
                                <option value="batiment">Bâtiment</option>
                            </select>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Comparison Results -->
        <div class="grid lg:grid-cols-2 gap-8 mb-8">
            <!-- Indépendante -->
            <div class="comparison-card bg-white rounded-3xl p-8 shadow-xl animate-fade-in">
                <div class="text-center mb-6">
                    <div class="text-5xl mb-3">🚀</div>
                    <h2 class="text-2xl font-bold text-gray-800 mb-2">Assistante Indépendante</h2>
                    <p class="text-green-600 font-semibold">Solution Flexible & Économique</p>
                </div>

                <div class="space-y-4 mb-6">
                    <div class="bg-gray-50 rounded-xl p-4">
                        <div class="flex justify-between items-center">
                            <span class="text-gray-700">Coût horaire</span>
                            <span class="font-bold text-gray-800" id="indie-hourly">35€</span>
                        </div>
                    </div>
                    <div class="bg-gray-50 rounded-xl p-4">
                        <div class="flex justify-between items-center">
                            <span class="text-gray-700">Coût mensuel</span>
                            <span class="font-bold text-gray-800" id="indie-monthly">2 800€</span>
                        </div>
                    </div>
                    <div class="bg-gray-50 rounded-xl p-4">
                        <div class="flex justify-between items-center">
                            <span class="text-gray-700">Coût annuel</span>
                            <span class="font-bold text-green-600 text-xl" id="indie-yearly">33 600€</span>
                        </div>
                    </div>
                </div>

                <div class="border-t pt-6">
                    <h3 class="font-bold text-gray-800 mb-3">✅ Avantages inclus:</h3>
                    <ul class="space-y-2 text-sm text-gray-600">
                        <li>• Aucune charge sociale</li>
                        <li>• Pas de congés payés à financer</li>
                        <li>• Flexibilité totale des horaires</li>
                        <li>• Expertise spécialisée</li>
                        <li>• Pas de matériel à fournir</li>
                        <li>• Arrêt immédiat si besoin</li>
                    </ul>
                </div>
            </div>

            <!-- Salariée -->
            <div class="comparison-card bg-white rounded-3xl p-8 shadow-xl animate-fade-in">
                <div class="text-center mb-6">
                    <div class="text-5xl mb-3">👩‍💼</div>
                    <h2 class="text-2xl font-bold text-gray-800 mb-2">Assistante Salariée</h2>
                    <p class="text-red-600 font-semibold">Coût Total Réel</p>
                </div>

                <div class="space-y-4 mb-6">
                    <div class="bg-red-50 rounded-xl p-4">
                        <div class="flex justify-between items-center">
                            <span class="text-gray-700">Salaire brut</span>
                            <span class="font-bold text-gray-800" id="employee-gross">2 200€</span>
                        </div>
                    </div>
                    <div class="bg-red-50 rounded-xl p-4">
                        <div class="flex justify-between items-center">
                            <span class="text-gray-700">Charges patronales</span>
                            <span class="font-bold text-red-600" id="employee-charges">946€</span>
                        </div>
                    </div>
                    <div class="bg-red-50 rounded-xl p-4">
                        <div class="flex justify-between items-center">
                            <span class="text-gray-700">Coût mensuel total</span>
                            <span class="font-bold text-gray-800" id="employee-monthly">3 146€</span>
                        </div>
                    </div>
                    <div class="bg-red-50 rounded-xl p-4">
                        <div class="flex justify-between items-center">
                            <span class="text-gray-700">Coût annuel total</span>
                            <span class="font-bold text-red-600 text-xl" id="employee-yearly">37 752€</span>
                        </div>
                    </div>
                </div>

                <div class="border-t pt-6">
                    <h3 class="font-bold text-gray-800 mb-3">⚠️ Coûts cachés:</h3>
                    <ul class="space-y-2 text-sm text-gray-600">
                        <li>• Charges sociales (43%)</li>
                        <li>• Congés payés (10%)</li>
                        <li>• Formation obligatoire</li>
                        <li>• Matériel et bureau</li>
                        <li>• Gestion administrative</li>
                        <li>• Risque prud'homal</li>
                    </ul>
                </div>
            </div>
        </div>

        <!-- Savings Summary -->
        <div class="glass-effect rounded-3xl p-8 mb-8 animate-fade-in">
            <div class="text-center mb-8">
                <h2 class="text-3xl font-bold text-white mb-4">💰 Vos Économies Réelles</h2>
                <div class="grid md:grid-cols-3 gap-6">
                    <div class="bg-white rounded-2xl p-6">
                        <div class="text-3xl mb-2">📅</div>
                        <p class="text-gray-600 text-sm">Économie mensuelle</p>
                        <p class="text-2xl font-bold savings-highlight" id="monthly-savings">346€</p>
                    </div>
                    <div class="bg-white rounded-2xl p-6">
                        <div class="text-3xl mb-2">📊</div>
                        <p class="text-gray-600 text-sm">Économie annuelle</p>
                        <p class="text-3xl font-bold savings-highlight" id="yearly-savings">4 152€</p>
                    </div>
                    <div class="bg-white rounded-2xl p-6">
                        <div class="text-3xl mb-2">📈</div>
                        <p class="text-gray-600 text-sm">Pourcentage d'économie</p>
                        <p class="text-2xl font-bold savings-highlight" id="savings-percent">11%</p>
                    </div>
                </div>
            </div>

            <div class="text-center">
                <button onclick="generateReport()" class="bg-gradient-to-r from-violet-600 to-fuchsia-500 text-white px-8 py-4 rounded-xl font-semibold hover:from-violet-700 hover:to-fuchsia-600 transition-all duration-300 shadow-lg hover:shadow-xl text-lg">
                    📋 Générer le Rapport Détaillé
                </button>
            </div>
        </div>

        <!-- Benefits Comparison -->
        <div class="grid md:grid-cols-4 gap-6 mb-8">
            <div class="bg-white rounded-2xl p-6 text-center animate-fade-in">
                <div class="benefit-icon">⚡</div>
                <h3 class="font-bold text-gray-800 mb-2">Réactivité</h3>
                <p class="text-sm text-gray-600">Démarrage immédiat, pas de période d'essai</p>
            </div>
            <div class="bg-white rounded-2xl p-6 text-center animate-fade-in">
                <div class="benefit-icon">🎯</div>
                <h3 class="font-bold text-gray-800 mb-2">Expertise</h3>
                <p class="text-sm text-gray-600">Spécialiste formée, outils à jour</p>
            </div>
            <div class="bg-white rounded-2xl p-6 text-center animate-fade-in">
                <div class="benefit-icon">📈</div>
                <h3 class="font-bold text-gray-800 mb-2">Flexibilité</h3>
                <p class="text-sm text-gray-600">Adaptation selon vos pics d'activité</p>
            </div>
            <div class="bg-white rounded-2xl p-6 text-center animate-fade-in">
                <div class="benefit-icon">🛡️</div>
                <h3 class="font-bold text-gray-800 mb-2">Sécurité</h3>
                <p class="text-sm text-gray-600">Pas de risque social, assurance pro</p>
            </div>
        </div>

        <!-- Report Section -->
        <div id="report-section" class="glass-effect rounded-3xl p-8 hidden animate-fade-in">
            <h2 class="text-2xl font-bold text-white mb-6 text-center">📊 Rapport Détaillé</h2>
            <div class="bg-white rounded-2xl p-8" id="report-content">
                <!-- Report content will be generated here -->
            </div>
        </div>

        <!-- Footer -->
        <div class="bg-gradient-to-r from-violet-900/80 to-purple-900/80 backdrop-blur-sm border border-white/10 rounded-3xl p-8 mt-8 animate-fade-in">
            <div class="text-center">
                <div class="flex flex-col md:flex-row items-center justify-center gap-8">
                    <div class="text-white">
                        <h3 class="text-xl font-bold mb-2">SChau-MY - Sylvie CHAUSSADAS</h3>
                        <p class="text-white/80 mb-4">Votre Assistante Administrative Indépendante</p>
                        <div class="flex flex-wrap justify-center gap-4 text-sm">
                            <span class="flex items-center gap-2">📞 06 28 90 01 14</span>
                            <span class="flex items-center gap-2">✉️ contact@sylvie-chaussadas.fr</span>
                        </div>
                    </div>
                    <div class="flex flex-col gap-3">
                        <a href="https://calendly.com/sylviechaussadas/reservez_votre_appel_decouverte_maintenant" target="_blank" rel="noopener noreferrer" 
                           class="bg-gradient-to-r from-violet-500 to-fuchsia-500 text-white px-6 py-3 rounded-xl font-semibold hover:from-violet-600 hover:to-fuchsia-600 transition-all duration-300 shadow-lg hover:shadow-xl">
                            📅 Réserver un RDV Gratuit
                        </a>
                        <div class="flex gap-2 justify-center">
                            <a href="https://sylvie-chaussadas.fr/" target="_blank" rel="noopener noreferrer" 
                               class="bg-white/20 text-white px-4 py-2 rounded-lg hover:bg-white/30 transition-all text-sm">
                                🌐 Site Web
                            </a>
                            <a href="https://www.linkedin.com/in/sylvie-chaussadas/" target="_blank" rel="noopener noreferrer" 
                               class="bg-white/20 text-white px-4 py-2 rounded-lg hover:bg-white/30 transition-all text-sm">
                                💼 LinkedIn
                            </a>
                        </div>
                    </div>
                </div>
                <div class="mt-6 pt-6 border-t border-white/20">
                    <p class="text-white/60 text-sm">
                        © 2024 SChau-MY - Tous droits réservés | Simulateur développé pour démontrer les avantages économiques de l'assistance administrative indépendante
                    </p>
                </div>
            </div>
        </div>
    </div>

    <script>
        function updateCalculation() {
            // Get input values
            const hours = parseInt(document.getElementById('hours-slider').value);
            const weeks = parseInt(document.getElementById('weeks-slider').value);
            const rate = parseInt(document.getElementById('rate-slider').value);
            const salary = parseInt(document.getElementById('salary-slider').value);
            const companySize = document.getElementById('company-size').value;
            
            // Update displays
            document.getElementById('hours-display').textContent = hours;
            document.getElementById('weeks-display').textContent = weeks;
            document.getElementById('rate-display').textContent = rate;
            document.getElementById('salary-display').textContent = salary;
            
            // Calculate independent costs
            const monthlyHours = (hours * weeks) / 12;
            const indieMonthly = monthlyHours * rate;
            const indieYearly = hours * weeks * rate;
            
            // Calculate employee costs
            let chargeRate = 0.43; // Default charge rate
            if (companySize === 'tpe') chargeRate = 0.43;
            else if (companySize === 'pe') chargeRate = 0.45;
            else chargeRate = 0.47;
            
            const employeeCharges = salary * chargeRate;
            const employeeMonthly = salary + employeeCharges;
            const employeeYearly = employeeMonthly * 12;
            
            // Calculate savings
            const monthlySavings = employeeMonthly - indieMonthly;
            const yearlySavings = employeeYearly - indieYearly;
            const savingsPercent = Math.round((yearlySavings / employeeYearly) * 100);
            
            // Update displays
            document.getElementById('indie-hourly').textContent = rate + '€';
            document.getElementById('indie-monthly').textContent = Math.round(indieMonthly).toLocaleString() + '€';
            document.getElementById('indie-yearly').textContent = Math.round(indieYearly).toLocaleString() + '€';
            
            document.getElementById('employee-gross').textContent = salary.toLocaleString() + '€';
            document.getElementById('employee-charges').textContent = Math.round(employeeCharges).toLocaleString() + '€';
            document.getElementById('employee-monthly').textContent = Math.round(employeeMonthly).toLocaleString() + '€';
            document.getElementById('employee-yearly').textContent = Math.round(employeeYearly).toLocaleString() + '€';
            
            document.getElementById('monthly-savings').textContent = Math.round(monthlySavings).toLocaleString() + '€';
            document.getElementById('yearly-savings').textContent = Math.round(yearlySavings).toLocaleString() + '€';
            document.getElementById('savings-percent').textContent = savingsPercent + '%';
        }
        
        function generateReport() {
            const hours = parseInt(document.getElementById('hours-slider').value);
            const weeks = parseInt(document.getElementById('weeks-slider').value);
            const rate = parseInt(document.getElementById('rate-slider').value);
            const salary = parseInt(document.getElementById('salary-slider').value);
            const companySize = document.getElementById('company-size').selectedOptions[0].text;
            const sector = document.getElementById('sector').selectedOptions[0].text;
            
            const indieYearly = document.getElementById('indie-yearly').textContent;
            const employeeYearly = document.getElementById('employee-yearly').textContent;
            const yearlySavings = document.getElementById('yearly-savings').textContent;
            const savingsPercent = document.getElementById('savings-percent').textContent;
            
            const currentDate = new Date().toLocaleDateString('fr-FR');
            
            const reportHTML = `
                <div class="text-center mb-8">
                    <div class="flex items-center justify-center gap-4 mb-4">
                        <div class="w-16 h-16 bg-white rounded-full flex items-center justify-center shadow-lg overflow-hidden">
                            <img src="https://sylvie-chaussadas.fr/wp-content/uploads/2025/04/Logo_Rond-transparent-250.png" 
                                 alt="Logo SChau-MY" 
                                 class="w-14 h-14 object-contain"
                                 onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                            <div class="w-14 h-14 brand-gradient rounded-full flex items-center justify-center text-white text-lg font-bold" style="display: none;">
                                <div class="text-center">
                                    <div class="text-lg font-extrabold">SC</div>
                                    <div class="text-xs -mt-1">hau-MY</div>
                                </div>
                            </div>
                        </div>
                        <div class="text-left">
                            <h3 class="text-2xl font-bold text-gray-800">SChau-MY</h3>
                            <p class="text-gray-600">Sylvie CHAUSSADAS</p>
                        </div>
                    </div>
                    <h3 class="text-3xl font-bold text-gray-800 mb-2">Rapport Comparatif</h3>
                    <p class="text-gray-600">Assistante Administrative - Généré le ${currentDate}</p>
                    <div class="mt-4 p-4 bg-purple-50 rounded-xl">
                        <p class="text-lg"><strong>Entreprise:</strong> ${companySize} - Secteur ${sector}</p>
                        <p class="text-lg"><strong>Besoin:</strong> ${hours}h/semaine sur ${weeks} semaines/an</p>
                    </div>
                </div>
                
                <div class="grid md:grid-cols-2 gap-8 mb-8">
                    <div class="border-2 border-green-200 rounded-xl p-6 bg-green-50">
                        <h4 class="text-xl font-bold text-green-800 mb-4">🚀 Solution Indépendante</h4>
                        <div class="space-y-3">
                            <div class="flex justify-between">
                                <span>Tarif horaire:</span>
                                <span class="font-bold">${rate}€/h</span>
                            </div>
                            <div class="flex justify-between">
                                <span>Coût annuel total:</span>
                                <span class="font-bold text-green-600">${indieYearly}</span>
                            </div>
                        </div>
                        <div class="mt-4 p-3 bg-green-100 rounded-lg">
                            <p class="text-sm font-semibold text-green-800">Avantages:</p>
                            <ul class="text-sm text-green-700 mt-2">
                                <li>• Flexibilité totale</li>
                                <li>• Expertise spécialisée</li>
                                <li>• Aucune charge sociale</li>
                                <li>• Démarrage immédiat</li>
                            </ul>
                        </div>
                    </div>
                    
                    <div class="border-2 border-red-200 rounded-xl p-6 bg-red-50">
                        <h4 class="text-xl font-bold text-red-800 mb-4">👩‍💼 Solution Salariée</h4>
                        <div class="space-y-3">
                            <div class="flex justify-between">
                                <span>Salaire brut:</span>
                                <span class="font-bold">${salary}€/mois</span>
                            </div>
                            <div class="flex justify-between">
                                <span>Coût annuel total:</span>
                                <span class="font-bold text-red-600">${employeeYearly}</span>
                            </div>
                        </div>
                        <div class="mt-4 p-3 bg-red-100 rounded-lg">
                            <p class="text-sm font-semibold text-red-800">Coûts cachés:</p>
                            <ul class="text-sm text-red-700 mt-2">
                                <li>• Charges sociales (43-47%)</li>
                                <li>• Congés payés</li>
                                <li>• Formation</li>
                                <li>• Matériel et bureau</li>
                            </ul>
                        </div>
                    </div>
                </div>
                
                <div class="bg-gradient-to-r from-green-100 to-purple-100 rounded-xl p-8 text-center">
                    <h4 class="text-2xl font-bold text-gray-800 mb-4">💰 Résultat Final</h4>
                    <div class="grid md:grid-cols-2 gap-6">
                        <div>
                            <p class="text-lg text-gray-700">Économie annuelle</p>
                            <p class="text-4xl font-bold text-green-600">${yearlySavings}</p>
                        </div>
                        <div>
                            <p class="text-lg text-gray-700">Pourcentage d'économie</p>
                            <p class="text-4xl font-bold text-green-600">${savingsPercent}</p>
                        </div>
                    </div>
                    <div class="mt-6 p-4 bg-white rounded-lg">
                        <p class="text-lg font-semibold text-gray-800">
                            En choisissant une assistante indépendante, vous économisez 
                            <span class="text-green-600 font-bold">${yearlySavings}</span> par an 
                            tout en bénéficiant d'une flexibilité et d'une expertise optimales.
                        </p>
                    </div>
                </div>
                
                <div class="mt-8 border-t pt-6">
                    <div class="bg-gradient-to-r from-purple-50 to-violet-50 rounded-xl p-6 mb-6">
                        <h4 class="text-xl font-bold text-gray-800 mb-4 text-center">📞 Contactez SChau-MY</h4>
                        <div class="grid md:grid-cols-2 gap-4 text-center">
                            <div>
                                <p class="font-semibold text-gray-800">Sylvie CHAUSSADAS</p>
                                <p class="text-gray-600">📞 06 28 90 01 14</p>
                                <p class="text-gray-600">✉️ contact@sylvie-chaussadas.fr</p>
                            </div>
                            <div>
                                <p class="font-semibold text-gray-800">Liens utiles</p>
                                <p class="text-gray-600">🌐 sylvie-chaussadas.fr</p>
                                <p class="text-gray-600">📅 Calendly: RDV gratuit disponible</p>
                            </div>
                        </div>
                    </div>
                    <div class="text-center">
                        <button onclick="window.print()" class="bg-violet-600 text-white px-8 py-3 rounded-xl font-semibold hover:bg-violet-700 transition-colors mr-4">
                            🖨️ Imprimer le Rapport
                        </button>
                        <a href="https://calendly.com/sylviechaussadas/reservez_votre_appel_decouverte_maintenant" target="_blank" rel="noopener noreferrer" 
                           class="bg-green-600 text-white px-8 py-3 rounded-xl font-semibold hover:bg-green-700 transition-colors inline-block">
                            📅 Prendre RDV
                        </a>
                    </div>
                </div>
            `;
            
            document.getElementById('report-content').innerHTML = reportHTML;
            document.getElementById('report-section').classList.remove('hidden');
            document.getElementById('report-section').scrollIntoView({ behavior: 'smooth' });
        }
        
        // Initialize calculation on page load
        updateCalculation();
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'98b613b565b4703e',t:'MTc1OTkzMTEwOC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
