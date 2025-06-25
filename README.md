<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AfriConnect - Réseau social pour l'Afrique Centrale</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #e67e22;
            --secondary: #16a085;
            --dark: #2c3e50;
            --light: #ecf0f1;
            --accent: #d35400;
            --success: #27ae60;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f5f5;
            color: var(--dark);
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        /* Header */
        header {
            background: linear-gradient(135deg, var(--primary), var(--accent));
            color: white;
            padding: 15px 0;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .logo i {
            font-size: 2rem;
        }
        
        .logo h1 {
            font-size: 1.8rem;
            font-weight: 700;
        }
        
        .nav-links {
            display: flex;
            gap: 25px;
        }
        
        .nav-links a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 5px;
        }
        
        .nav-links a:hover {
            transform: translateY(-2px);
        }
        
        .user-actions {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .btn {
            padding: 10px 20px;
            border-radius: 30px;
            border: none;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 1rem;
        }
        
        .btn-primary {
            background-color: var(--secondary);
            color: white;
        }
        
        .btn-outline {
            background-color: transparent;
            border: 2px solid white;
            color: white;
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        /* Hero Section */
        .hero {
            background: url('https://images.unsplash.com/photo-1507699622108-4be3abd695ad?q=80&w=2071') no-repeat center center/cover;
            height: 500px;
            display: flex;
            align-items: center;
            position: relative;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
        }
        
        .hero-content {
            position: relative;
            color: white;
            max-width: 600px;
            padding: 30px;
            background: rgba(44, 62, 80, 0.8);
            border-radius: 10px;
            margin-left: 50px;
        }
        
        .hero-content h2 {
            font-size: 2.5rem;
            margin-bottom: 20px;
            line-height: 1.2;
        }
        
        .hero-content p {
            font-size: 1.2rem;
            margin-bottom: 30px;
        }
        
        /* Features */
        .features {
            padding: 80px 0;
            background-color: var(--light);
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
            font-size: 2rem;
            color: var(--dark);
            position: relative;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background-color: var(--primary);
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .feature-card {
            background: white;
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: all 0.3s ease;
            text-align: center;
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }
        
        .feature-icon {
            font-size: 3rem;
            color: var(--primary);
            margin-bottom: 20px;
        }
        
        .feature-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--dark);
        }
        
        /* Countries */
        .countries {
            padding: 80px 0;
            background: linear-gradient(to right, var(--secondary), var(--primary));
            color: white;
        }
        
        .countries-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 40px;
        }
        
        .country-card {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            padding: 20px;
            text-align: center;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }
        
        .country-card:hover {
            transform: scale(1.05);
            background: rgba(255, 255, 255, 0.2);
        }
        
        .country-card i {
            font-size: 2.5rem;
            margin-bottom: 15px;
        }
        
        /* Feed */
        .feed {
            padding: 80px 0;
            background-color: white;
        }
        
        .feed-container {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .post-form {
            background: var(--light);
            padding: 25px;
            border-radius: 10px;
            margin-bottom: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }
        
        .post-form textarea {
            width: 100%;
            height: 100px;
            padding: 15px;
            border: 1px solid #ddd;
            border-radius: 10px;
            resize: vertical;
            font-size: 1rem;
            margin-bottom: 15px;
        }
        
        .post-form button {
            background-color: var(--primary);
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 30px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
        }
        
        .post-form button:hover {
            background-color: var(--accent);
        }
        
        .post {
            background: white;
            border-radius: 10px;
            padding: 25px;
            margin-bottom: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            position: relative;
        }
        
        .post-header {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
        }
        
        .post-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background-color: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            font-size: 1.2rem;
            margin-right: 15px;
        }
        
        .post-user {
            font-weight: 600;
            color: var(--dark);
        }
        
        .post-time {
            color: #7f8c8d;
            font-size: 0.9rem;
        }
        
        .post-content {
            margin-bottom: 20px;
            line-height: 1.7;
        }
        
        .post-image {
            width: 100%;
            border-radius: 10px;
            margin-bottom: 20px;
        }
        
        .post-actions {
            display: flex;
            gap: 20px;
            border-top: 1px solid #eee;
            padding-top: 15px;
        }
        
        .post-action {
            display: flex;
            align-items: center;
            gap: 5px;
            color: #7f8c8d;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .post-action:hover {
            color: var(--primary);
        }
        
        /* Footer */
        footer {
            background-color: var(--dark);
            color: white;
            padding: 60px 0 30px;
        }
        
        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }
        
        .footer-column h3 {
            font-size: 1.3rem;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-column h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 50px;
            height: 2px;
            background-color: var(--primary);
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 10px;
        }
        
        .footer-links a {
            color: #bdc3c7;
            text-decoration: none;
            transition: all 0.3s ease;
        }
        
        .footer-links a:hover {
            color: var(--primary);
            padding-left: 5px;
        }
        
        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }
        
        .social-links a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            color: white;
            transition: all 0.3s ease;
        }
        
        .social-links a:hover {
            background-color: var(--primary);
            transform: translateY(-3px);
        }
        
        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #bdc3c7;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .header-container {
                flex-direction: column;
                gap: 15px;
            }
            
            .hero-content {
                margin: 0 auto;
                text-align: center;
            }
            
            .nav-links {
                flex-wrap: wrap;
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-container">
            <div class="logo">
                <i class="fas fa-users"></i>
                <h1>AfriConnect</h1>
            </div>
            <div class="nav-links">
                <a href="#"><i class="fas fa-home"></i> Accueil</a>
                <a href="#"><i class="fas fa-user-friends"></i> Rencontres</a>
                <a href="#"><i class="fas fa-comments"></i> Discussions</a>
                <a href="#"><i class="fas fa-camera"></i> Moments</a>
            </div>
            <div class="user-actions">
                <button class="btn btn-outline">Connexion</button>
                <button class="btn btn-primary">Inscription</button>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h2>Connectez-vous, Partagez et Rencontrez en Afrique Centrale</h2>
            <p>Rejoignez la communauté qui célèbre la richesse culturelle de l'Afrique Centrale. Partagez vos moments, rencontrez des personnes passionnantes et échangez des idées.</p>
            <button class="btn btn-primary">Commencer maintenant</button>
        </div>
    </section>

    <!-- Features -->
    <section class="features">
        <div class="container">
            <h2 class="section-title">Nos Fonctionnalités</h2>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-heart"></i>
                    </div>
                    <h3>Rencontres</h3>
                    <p>Trouvez des personnes partageant les mêmes centres d'intérêt dans votre région ou à travers l'Afrique Centrale.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-comments"></i>
                    </div>
                    <h3>Discussions</h3>
                    <p>Participez à des conversations enrichissantes sur des sujets qui vous passionnent.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-share-alt"></i>
                    </div>
                    <h3>Partage d'idées</h3>
                    <p>Échangez vos réflexions, projets et visions pour l'avenir de l'Afrique Centrale.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-camera"></i>
                    </div>
                    <h3>Moments</h3>
                    <p>Partagez vos expériences quotidiennes à travers des photos et des récits.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Countries -->
    <section class="countries">
        <div class="container">
            <h2 class="section-title">Pour les Pays d'Afrique Centrale</h2>
            <div class="countries-grid">
                <div class="country-card">
                    <i class="fas fa-flag"></i>
                    <h3>Cameroun</h3>
                </div>
                <div class="country-card">
                    <i class="fas fa-flag"></i>
                    <h3>Tchad</h3>
                </div>
                <div class="country-card">
                    <i class="fas fa-flag"></i>
                    <h3>République Centrafricaine</h3>
                </div>
                <div class="country-card">
                    <i class="fas fa-flag"></i>
                    <h3>Congo-Brazzaville</h3>
                </div>
                <div class="country-card">
                    <i class="fas fa-flag"></i>
                    <h3>République Démocratique du Congo</h3>
                </div>
                <div class="country-card">
                    <i class="fas fa-flag"></i>
                    <h3>Gabon</h3>
                </div>
                <div class="country-card">
                    <i class="fas fa-flag"></i>
                    <h3>Guinée Équatoriale</h3>
                </div>
                <div class="country-card">
                    <i class="fas fa-flag"></i>
                    <h3>São Tomé-et-Príncipe</h3>
                </div>
            </div>
        </div>
    </section>

    <!-- Feed -->
    <section class="feed">
        <div class="container">
            <h2 class="section-title">Fil d'Actualités</h2>
            <div class="feed-container">
                <div class="post-form">
                    <textarea placeholder="Partagez un moment, une idée ou une pensée..."></textarea>
                    <div style="display: flex; justify-content: space-between; align-items: center;">
                        <div>
                            <button style="background: transparent; color: var(--dark); padding: 0;"><i class="fas fa-image"></i> Photo</button>
                            <button style="background: transparent; color: var(--dark); padding: 0; margin-left: 15px;"><i class="fas fa-map-marker-alt"></i> Lieu</button>
                        </div>
                        <button>Publier</button>
                    </div>
                </div>
                
                <div class="post">
                    <div class="post-header">
                        <div class="post-avatar">JD</div>
                        <div>
                            <div class="post-user">Jean Didier</div>
                            <div class="post-time">Il y a 2 heures • Yaoundé, Cameroun</div>
                        </div>
                    </div>
                    <div class="post-content">
                        <p>Magnifique coucher de soleil à Limbé aujourd'hui. La nature nous offre des spectacles incroyables ! 🌅 #Cameroun #Nature #Afrique</p>
                    </div>
                    <img src="https://images.unsplash.com/photo-1560264281-5b74e2d6d1a1?q=80&w=2070" alt="Coucher de soleil" class="post-image">
                    <div class="post-actions">
                        <div class="post-action"><i class="fas fa-heart"></i> 42</div>
                        <div class="post-action"><i class="fas fa-comment"></i> 8</div>
                        <div class="post-action"><i class="fas fa-share"></i> Partager</div>
                    </div>
                </div>
                
                <div class="post">
                    <div class="post-header">
                        <div class="post-avatar">AM</div>
                        <div>
                            <div class="post-user">Amina Moussa</div>
                            <div class="post-time">Hier • N'Djamena, Tchad</div>
                        </div>
                    </div>
                    <div class="post-content">
                        <p>Je cherche à connecter avec des entrepreneurs dans le domaine agricole en Afrique Centrale. J'ai un projet d'agro-transformation qui pourrait bénéficier à plusieurs communautés. Contactez-moi si intéressé! 🌱 #Entrepreneuriat #Agriculture #Tchad</p>
                    </div>
                    <div class="post-actions">
                        <div class="post-action"><i class="fas fa-heart"></i> 78</div>
                        <div class="post-action"><i class="fas fa-comment"></i> 24</div>
                        <div class="post-action"><i class="fas fa-share"></i> Partager</div>
                    </div>
                </div>
                
                <div class="post">
                    <div class="post-header">
                        <div class="post-avatar">PB</div>
                        <div>
                            <div class="post-user">Paul Bouanga</div>
                            <div class="post-time">Il y a 3 jours • Libreville, Gabon</div>
                        </div>
                    </div>
                    <div class="post-content">
                        <p>Notre groupe de discussion sur l'histoire de l'Afrique Centrale se réunira samedi prochain. Nous aborderons les royaumes pré-coloniaux. Tout le monde est le bienvenu! 📚 #Histoire #Culture #Gabon</p>
                    </div>
                    <img src="https://images.unsplash.com/photo-1547471080-7cc2caa01a7e?q=80&w=2071" alt="Livre d'histoire" class="post-image">
                    <div class="post-actions">
                        <div class="post-action"><i class="fas fa-heart"></i> 56</div>
                        <div class="post-action"><i class="fas fa-comment"></i> 17</div>
                        <div class="post-action"><i class="fas fa-share"></i> Partager</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-grid">
                <div class="footer-column">
                    <h3>AfriConnect</h3>
                    <p>La plateforme de rencontre, communication et partage dédiée aux peuples d'Afrique Centrale.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                    </div>
                </div>
                <div class="footer-column">
                    <h3>Liens Rapides</h3>
                    <ul class="footer-links">
                        <li><a href="#">Accueil</a></li>
                        <li><a href="#">À propos</a></li>
                        <li><a href="#">Fonctionnalités</a></li>
                        <li><a href="#">Communauté</a></li>
                        <li><a href="#">Blog</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Support</h3>
                    <ul class="footer-links">
                        <li><a href="#">Centre d'aide</a></li>
                        <li><a href="#">FAQ</a></li>
                        <li><a href="#">Contact</a></li>
                        <li><a href="#">Politique de confidentialité</a></li>
                        <li><a href="#">Conditions d'utilisation</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Newsletter</h3>
                    <p>Inscrivez-vous pour recevoir nos dernières actualités et mises à jour.</p>
                    <form style="margin-top: 15px;">
                        <input type="email" placeholder="Votre email" style="width: 100%; padding: 10px; border-radius: 5px; border: none; margin-bottom: 10px;">
                        <button class="btn btn-primary" style="width: 100%;">S'abonner</button>
                    </form>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 AfriConnect. Tous droits réservés. Conçu avec ❤️ pour l'Afrique Centrale.</p>
            </div>
        </div>
    </footer>

    <script>
        // Simulation de fonctionnalités interactives
        document.addEventListener('DOMContentLoaded', function() {
            // Animation des cartes au défilement
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = 1;
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            }, { threshold: 0.1 });
            
            document.querySelectorAll('.feature-card, .country-card, .post').forEach(card => {
                card.style.opacity = 0;
                card.style.transform = 'translateY(20px)';
                card.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
                observer.observe(card);
            });
            
            // Bouton "J'aime"
            document.querySelectorAll('.post-action').forEach(action => {
                if (action.querySelector('.fa-heart')) {
                    action.addEventListener('click', function() {
                        const heart = this.querySelector('i');
                        if (heart.classList.contains('fas')) {
                            heart.classList.remove('fas');
                            heart.classList.add('far');
                        } else {
                            heart.classList.remove('far');
                            heart.classList.add('fas');
                            heart.style.color = '#e74c3c';
                        }
                    });
                }
            });
        });
    </script>
</body>
</html><!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AfriConnect - Réseau social pour l'Afrique Centrale</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #e67e22;
            --secondary: #16a085;
            --dark: #2c3e50;
            --light: #ecf0f1;
            --accent: #d35400;
            --success: #27ae60;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f5f5;
            color: var(--dark);
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        /* Header */
        header {
            background: linear-gradient(135deg, var(--primary), var(--accent));
            color: white;
            padding: 15px 0;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .logo i {
            font-size: 2rem;
        }
        
        .logo h1 {
            font-size: 1.8rem;
            font-weight: 700;
        }
        
        .nav-links {
            display: flex;
            gap: 25px;
        }
        
        .nav-links a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 5px;
        }
        
        .nav-links a:hover {
            transform: translateY(-2px);
        }
        
        .user-actions {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .btn {
            padding: 10px 20px;
            border-radius: 30px;
            border: none;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 1rem;
        }
        
        .btn-primary {
            background-color: var(--secondary);
            color: white;
        }
        
        .btn-outline {
            background-color: transparent;
            border: 2px solid white;
            color: white;
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        /* Hero Section */
        .hero {
            background: url('https://images.unsplash.com/photo-1507699622108-4be3abd695ad?q=80&w=2071') no-repeat center center/cover;
            height: 500px;
            display: flex;
            align-items: center;
            position: relative;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
        }
        
        .hero-content {
            position: relative;
            color: white;
            max-width: 600px;
            padding: 30px;
            background: rgba(44, 62, 80, 0.8);
            border-radius: 10px;
            margin-left: 50px;
        }
        
        .hero-content h2 {
            font-size: 2.5rem;
            margin-bottom: 20px;
            line-height: 1.2;
        }
        
        .hero-content p {
            font-size: 1.2rem;
            margin-bottom: 30px;
        }
        
        /* Features */
        .features {
            padding: 80px 0;
            background-color: var(--light);
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
            font-size: 2rem;
            color: var(--dark);
            position: relative;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background-color: var(--primary);
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .feature-card {
            background: white;
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: all 0.3s ease;
            text-align: center;
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }
        
        .feature-icon {
            font-size: 3rem;
            color: var(--primary);
            margin-bottom: 20px;
        }
        
        .feature-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--dark);
        }
        
        /* Countries */
        .countries {
            padding: 80px 0;
            background: linear-gradient(to right, var(--secondary), var(--primary));
            color: white;
        }
        
        .countries-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 40px;
        }
        
        .country-card {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            padding: 20px;
            text-align: center;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }
        
        .country-card:hover {
            transform: scale(1.05);
            background: rgba(255, 255, 255, 0.2);
        }
        
        .country-card i {
            font-size: 2.5rem;
            margin-bottom: 15px;
        }
        
        /* Feed */
        .feed {
            padding: 80px 0;
            background-color: white;
        }
        
        .feed-container {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .post-form {
            background: var(--light);
            padding: 25px;
            border-radius: 10px;
            margin-bottom: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }
        
        .post-form textarea {
            width: 100%;
            height: 100px;
            padding: 15px;
            border: 1px solid #ddd;
            border-radius: 10px;
            resize: vertical;
            font-size: 1rem;
            margin-bottom: 15px;
        }
        
        .post-form button {
            background-color: var(--primary);
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 30px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
        }
        
        .post-form button:hover {
            background-color: var(--accent);
        }
        
        .post {
            background: white;
            border-radius: 10px;
            padding: 25px;
            margin-bottom: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            position: relative;
        }
        
        .post-header {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
        }
        
        .post-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background-color: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            font-size: 1.2rem;
            margin-right: 15px;
        }
        
        .post-user {
            font-weight: 600;
            color: var(--dark);
        }
        
        .post-time {
            color: #7f8c8d;
            font-size: 0.9rem;
        }
        
        .post-content {
            margin-bottom: 20px;
            line-height: 1.7;
        }
        
        .post-image {
            width: 100%;
            border-radius: 10px;
            margin-bottom: 20px;
        }
        
        .post-actions {
            display: flex;
            gap: 20px;
            border-top: 1px solid #eee;
            padding-top: 15px;
        }
        
        .post-action {
            display: flex;
            align-items: center;
            gap: 5px;
            color: #7f8c8d;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .post-action:hover {
            color: var(--primary);
        }
        
        /* Footer */
        footer {
            background-color: var(--dark);
            color: white;
            padding: 60px 0 30px;
        }
        
        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }
        
        .footer-column h3 {
            font-size: 1.3rem;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-column h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 50px;
            height: 2px;
            background-color: var(--primary);
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 10px;
        }
        
        .footer-links a {
            color: #bdc3c7;
            text-decoration: none;
            transition: all 0.3s ease;
        }
        
        .footer-links a:hover {
            color: var(--primary);
            padding-left: 5px;
        }
        
        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }
        
        .social-links a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            color: white;
            transition: all 0.3s ease;
        }
        
        .social-links a:hover {
            background-color: var(--primary);
            transform: translateY(-3px);
        }
        
        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #bdc3c7;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .header-container {
                flex-direction: column;
                gap: 15px;
            }
            
            .hero-content {
                margin: 0 auto;
                text-align: center;
            }
            
            .nav-links {
                flex-wrap: wrap;
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-container">
            <div class="logo">
                <i class="fas fa-users"></i>
                <h1>AfriConnect</h1>
            </div>
            <div class="nav-links">
                <a href="#"><i class="fas fa-home"></i> Accueil</a>
                <a href="#"><i class="fas fa-user-friends"></i> Rencontres</a>
                <a href="#"><i class="fas fa-comments"></i> Discussions</a>
                <a href="#"><i class="fas fa-camera"></i> Moments</a>
            </div>
            <div class="user-actions">
                <button class="btn btn-outline">Connexion</button>
                <button class="btn btn-primary">Inscription</button>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h2>Connectez-vous, Partagez et Rencontrez en Afrique Centrale</h2>
            <p>Rejoignez la communauté qui célèbre la richesse culturelle de l'Afrique Centrale. Partagez vos moments, rencontrez des personnes passionnantes et échangez des idées.</p>
            <button class="btn btn-primary">Commencer maintenant</button>
        </div>
    </section>

    <!-- Features -->
    <section class="features">
        <div class="container">
            <h2 class="section-title">Nos Fonctionnalités</h2>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-heart"></i>
                    </div>
                    <h3>Rencontres</h3>
                    <p>Trouvez des personnes partageant les mêmes centres d'intérêt dans votre région ou à travers l'Afrique Centrale.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-comments"></i>
                    </div>
                    <h3>Discussions</h3>
                    <p>Participez à des conversations enrichissantes sur des sujets qui vous passionnent.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-share-alt"></i>
                    </div>
                    <h3>Partage d'idées</h3>
                    <p>Échangez vos réflexions, projets et visions pour l'avenir de l'Afrique Centrale.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-camera"></i>
                    </div>
                    <h3>Moments</h3>
                    <p>Partagez vos expériences quotidiennes à travers des photos et des récits.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Countries -->
    <section class="countries">
        <div class="container">
            <h2 class="section-title">Pour les Pays d'Afrique Centrale</h2>
            <div class="countries-grid">
                <div class="country-card">
                    <i class="fas fa-flag"></i>
                    <h3>Cameroun</h3>
                </div>
                <div class="country-card">
                    <i class="fas fa-flag"></i>
                    <h3>Tchad</h3>
                </div>
                <div class="country-card">
                    <i class="fas fa-flag"></i>
                    <h3>République Centrafricaine</h3>
                </div>
                <div class="country-card">
                    <i class="fas fa-flag"></i>
                    <h3>Congo-Brazzaville</h3>
                </div>
                <div class="country-card">
                    <i class="fas fa-flag"></i>
                    <h3>République Démocratique du Congo</h3>
                </div>
                <div class="country-card">
                    <i class="fas fa-flag"></i>
                    <h3>Gabon</h3>
                </div>
                <div class="country-card">
                    <i class="fas fa-flag"></i>
                    <h3>Guinée Équatoriale</h3>
                </div>
                <div class="country-card">
                    <i class="fas fa-flag"></i>
                    <h3>São Tomé-et-Príncipe</h3>
                </div>
            </div>
        </div>
    </section>

    <!-- Feed -->
    <section class="feed">
        <div class="container">
            <h2 class="section-title">Fil d'Actualités</h2>
            <div class="feed-container">
                <div class="post-form">
                    <textarea placeholder="Partagez un moment, une idée ou une pensée..."></textarea>
                    <div style="display: flex; justify-content: space-between; align-items: center;">
                        <div>
                            <button style="background: transparent; color: var(--dark); padding: 0;"><i class="fas fa-image"></i> Photo</button>
                            <button style="background: transparent; color: var(--dark); padding: 0; margin-left: 15px;"><i class="fas fa-map-marker-alt"></i> Lieu</button>
                        </div>
                        <button>Publier</button>
                    </div>
                </div>
                
                <div class="post">
                    <div class="post-header">
                        <div class="post-avatar">JD</div>
                        <div>
                            <div class="post-user">Jean Didier</div>
                            <div class="post-time">Il y a 2 heures • Yaoundé, Cameroun</div>
                        </div>
                    </div>
                    <div class="post-content">
                        <p>Magnifique coucher de soleil à Limbé aujourd'hui. La nature nous offre des spectacles incroyables ! 🌅 #Cameroun #Nature #Afrique</p>
                    </div>
                    <img src="https://images.unsplash.com/photo-1560264281-5b74e2d6d1a1?q=80&w=2070" alt="Coucher de soleil" class="post-image">
                    <div class="post-actions">
                        <div class="post-action"><i class="fas fa-heart"></i> 42</div>
                        <div class="post-action"><i class="fas fa-comment"></i> 8</div>
                        <div class="post-action"><i class="fas fa-share"></i> Partager</div>
                    </div>
                </div>
                
                <div class="post">
                    <div class="post-header">
                        <div class="post-avatar">AM</div>
                        <div>
                            <div class="post-user">Amina Moussa</div>
                            <div class="post-time">Hier • N'Djamena, Tchad</div>
                        </div>
                    </div>
                    <div class="post-content">
                        <p>Je cherche à connecter avec des entrepreneurs dans le domaine agricole en Afrique Centrale. J'ai un projet d'agro-transformation qui pourrait bénéficier à plusieurs communautés. Contactez-moi si intéressé! 🌱 #Entrepreneuriat #Agriculture #Tchad</p>
                    </div>
                    <div class="post-actions">
                        <div class="post-action"><i class="fas fa-heart"></i> 78</div>
                        <div class="post-action"><i class="fas fa-comment"></i> 24</div>
                        <div class="post-action"><i class="fas fa-share"></i> Partager</div>
                    </div>
                </div>
                
                <div class="post">
                    <div class="post-header">
                        <div class="post-avatar">PB</div>
                        <div>
                            <div class="post-user">Paul Bouanga</div>
                            <div class="post-time">Il y a 3 jours • Libreville, Gabon</div>
                        </div>
                    </div>
                    <div class="post-content">
                        <p>Notre groupe de discussion sur l'histoire de l'Afrique Centrale se réunira samedi prochain. Nous aborderons les royaumes pré-coloniaux. Tout le monde est le bienvenu! 📚 #Histoire #Culture #Gabon</p>
                    </div>
                    <img src="https://images.unsplash.com/photo-1547471080-7cc2caa01a7e?q=80&w=2071" alt="Livre d'histoire" class="post-image">
                    <div class="post-actions">
                        <div class="post-action"><i class="fas fa-heart"></i> 56</div>
                        <div class="post-action"><i class="fas fa-comment"></i> 17</div>
                        <div class="post-action"><i class="fas fa-share"></i> Partager</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-grid">
                <div class="footer-column">
                    <h3>AfriConnect</h3>
                    <p>La plateforme de rencontre, communication et partage dédiée aux peuples d'Afrique Centrale.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                    </div>
                </div>
                <div class="footer-column">
                    <h3>Liens Rapides</h3>
                    <ul class="footer-links">
                        <li><a href="#">Accueil</a></li>
                        <li><a href="#">À propos</a></li>
                        <li><a href="#">Fonctionnalités</a></li>
                        <li><a href="#">Communauté</a></li>
                        <li><a href="#">Blog</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Support</h3>
                    <ul class="footer-links">
                        <li><a href="#">Centre d'aide</a></li>
                        <li><a href="#">FAQ</a></li>
                        <li><a href="#">Contact</a></li>
                        <li><a href="#">Politique de confidentialité</a></li>
                        <li><a href="#">Conditions d'utilisation</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Newsletter</h3>
                    <p>Inscrivez-vous pour recevoir nos dernières actualités et mises à jour.</p>
                    <form style="margin-top: 15px;">
                        <input type="email" placeholder="Votre email" style="width: 100%; padding: 10px; border-radius: 5px; border: none; margin-bottom: 10px;">
                        <button class="btn btn-primary" style="width: 100%;">S'abonner</button>
                    </form>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 AfriConnect. Tous droits réservés. Conçu avec ❤️ pour l'Afrique Centrale.</p>
            </div>
        </div>
    </footer>

    <script>
        // Simulation de fonctionnalités interactives
        document.addEventListener('DOMContentLoaded', function() {
            // Animation des cartes au défilement
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = 1;
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            }, { threshold: 0.1 });
            
            document.querySelectorAll('.feature-card, .country-card, .post').forEach(card => {
                card.style.opacity = 0;
                card.style.transform = 'translateY(20px)';
                card.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
                observer.observe(card);
            });
            
            // Bouton "J'aime"
            document.querySelectorAll('.post-action').forEach(action => {
                if (action.querySelector('.fa-heart')) {
                    action.addEventListener('click', function() {
                        const heart = this.querySelector('i');
                        if (heart.classList.contains('fas')) {
                            heart.classList.remove('fas');
                            heart.classList.add('far');
                        } else {
                            heart.classList.remove('far');
                            heart.classList.add('fas');
                            heart.style.color = '#e74c3c';
                        }
                    });
                }
            });
        });
    </script>
</body>
<![1000113339](https://github.com/user-attachments/assets/ebdd3d58-828c-47f5-8915-76556f10366e)
/html>
