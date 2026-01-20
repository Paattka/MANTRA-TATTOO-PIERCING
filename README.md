# MANTRA-TATTOO-PIERCING
MANTRA TATTOO &amp; PIERCING
<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MANTRA TATTOO & PIERCING | TATTOO & PIERCING</title>
    
    <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.css" />
    
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@400;700&family=Cormorant+Garamond:ital,wght@0,300;0,400;1,300&display=swap');

        html { scroll-behavior: smooth; }
       body {
    background: radial-gradient(circle at center, #0a0f0e 0%, #040807 100%);
    background-attachment: fixed; /* Tło stoi w miejscu, gdy scrollujesz */
    color: #d4bc8e;
    font-family: 'Cormorant Garamond', serif;
    margin: 0; padding: 0; line-height: 1.6; overflow-x: hidden;
    box-shadow: inset 0 0 200px rgba(0,0,0,0.9);
}
body::before {
        content: "";
        position: fixed;
        top: 0; left: 0; width: 100%; height: 100%;
        background-image: url('https://www.transparenttextures.com/patterns/stardust.png');
        opacity: 0.15;
        pointer-events: none;
        z-index: -1;
    }

        /* --- MENU --- */
       nav {
            position: sticky;
            top: 0;
            background: linear-gradient(to bottom, rgba(18, 22, 21, 0.98), rgba(4, 8, 7, 0.95));
            padding: 15px 0;
            z-index: 1000;
            text-align: center;
            border-bottom: 1px solid #af944d;
        }
        .nav-container { display: flex; justify-content: center; align-items: center; gap: 15px; flex-wrap: wrap; }
        
        nav a {
            color: #d4bc8e; 
            text-decoration: none; 
            text-transform: uppercase;
            font-size: 0.8rem; 
            letter-spacing: 2px; 
            transition: 0.3s; 
            font-family: 'Cinzel', serif;
            position: relative; /* Potrzebne do pozycjonowania linii */
            padding-bottom: 4px;
        }

        /* Tworzenie linii, która pojawi się po najechaniu */
        nav a::after {
            content: '';
            position: absolute;
            width: 0; /* Linia startuje od zera */
            height: 1px;
            bottom: 0;
            left: 0;
            background-color: #af944d; /* Złoty kolor podkreślenia */
            transition: width 0.3s ease-in-out; /* Animacja rozwijania */
        }

        nav a:hover { 
            color: #fff; 
            text-shadow: 0 0 8px #af944d; 
        }

        /* Rozwinięcie linii do 100% szerokości po najechaniu */
        nav a:hover::after {
            width: 100%;
        }

        .nav-home { font-size: 1.5rem; color: #af944d !important; margin-right: 10px; line-height: 1; }
        
        /* Opcjonalne: Wyłączenie podkreślenia dla ikonki Ankh */
        .nav-home::after { display: none; }

        /* --- DEKORACJE --- */
        .gothic-divider {
            display: flex; align-items: center; justify-content: center;
            margin: 20px auto; color: #af944d; font-size: 1.5rem;
        }
        .gothic-divider::before, .gothic-divider::after {
            content: ""; width: 80px; height: 1px; background: linear-gradient(to right, transparent, #af944d, transparent); margin: 0 15px;
        }
        .corner {
            position: absolute; width: 20px; height: 20px; border: 1px solid #af944d; opacity: 0.4; pointer-events: none;
        }
        .top-left { top: 10px; left: 10px; border-right: none; border-bottom: none; }
        .top-right { top: 10px; right: 10px; border-left: none; border-bottom: none; }
        .bottom-left { bottom: 10px; left: 10px; border-right: none; border-top: none; }
        .bottom-right { bottom: 10px; right: 10px; border-left: none; border-top: none; }

        section { padding: 100px 20px; max-width: 1200px; margin: 0 auto; }
        h2 { font-family: 'Cinzel', serif; text-align: center; letter-spacing: 5px; color: #fff; font-size: 2.2rem; margin-bottom: 10px; }

        /* --- 3. ARTYŚCI (SYMETRIA 3+2) --- */
        .team-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 30px;
            max-width: 1000px;
            margin: 0 auto;
        }
        .artist-card {
    position: relative; 
    text-align: center; 
    padding: 30px 15px;
    background: rgba(212, 188, 142, 0.01); 
    border: 1px solid rgba(175, 148, 77, 0.1);
    flex: 0 1 calc(33.33% - 30px);
    min-width: 250px;
    transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
    overflow: hidden;
}
.artist-card:hover .top-left { transform: translate(-10px, -10px); opacity: 1; }
.artist-card:hover .top-right { transform: translate(10px, -10px); opacity: 1; }
.artist-card:hover .bottom-left { transform: translate(-10px, 10px); opacity: 1; }
.artist-card:hover .bottom-right { transform: translate(10px, 10px); opacity: 1; }

.artist-card:hover {
    background: rgba(175, 148, 77, 0.05);
    border-color: rgba(175, 148, 77, 0.5);
    transform: translateY(-10px); /* Delikatne uniesienie */
}

.artist-photo img { 
    width: 100%; 
    height: 100%; 
    object-fit: cover; 
    filter: grayscale(1) contrast(1.1); /* Mocniejszy kontrast czarno-biały */
    transition: 0.8s ease;
}

.artist-card:hover .artist-photo img { 
    filter: grayscale(0) contrast(1); /* Powrót do koloru */
    transform: scale(1.05);
}
        /* --- 4. GALERIA (2x4) --- */
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 15px;
        }
        @media (max-width: 768px) { .gallery-grid { grid-template-columns: repeat(2, 1fr); } }
        .gallery-item { aspect-ratio: 1/1; border: 1px solid rgba(175, 148, 77, 0.2); overflow: hidden; }
        .gallery-item img { width: 100%; height: 100%; object-fit: cover; transition: 0.6s; }
        .gallery-item:hover img { transform: scale(1.1); filter: brightness(1.2); }

       /* --- 2. CENNIK KARUZELA (POPRAWIONA) --- */
.swiper {
    width: 100%;
    padding: 50px 0;
}

.swiper-slide {
    transition: 0.5s;
    filter: blur(5px) opacity(0.2); /* Efekt rozmycia i przezroczystości */
    transform: scale(0.8); /* Zmniejszenie rozmiaru */
    display: flex;
    justify-content: center;
}

.swiper-slide-active {
    filter: blur(0) opacity(1); /* Brak efektu na aktywnym slajdzie */
    transform: scale(1); /* Powiększenie aktywnego slajdu */
}

.price-card {
    background: #0a0f0e; /* Kolor tła */
    border: 1px solid #af944d; /* Kolor obramowania */
    padding: 40px;
    width: 100%;
    max-width: 450px;
    position: relative; /* Pozycjonowanie względne */
}

.price-item {
    display: flex;
    justify-content: space-between; /* Rozmieszczenie elementów */
    padding: 10px 0;
    border-bottom: 1px solid rgba(175, 148, 77, 0.1); /* Delikatna linia dolna */
}

.swiper-button-next,
.swiper-button-prev {
    color: #af944d !important; /* Kolor przycisków nawigacyjnych */
}
        /* --- 6. NEWSLETTER (PROSTOKĄT) --- */
        .newsletter-input {
            background: rgba(212, 188, 142, 0.03);
            border: 1px solid rgba(175, 148, 77, 0.3);
            color: #fff; padding: 15px 30px; width: 320px;
            text-align: center; outline: none; transition: 0.4s;
            font-family: 'Cinzel', serif;
        }
        .newsletter-input:focus {
            background: rgba(175, 148, 77, 0.08);
            border: 1px solid #af944d;
            box-shadow: 0 0 20px rgba(175, 148, 77, 0.2);
        }
        .submit-btn {
            background: transparent; color: #af944d; border: 1px solid #af944d;
            padding: 12px 40px; cursor: pointer; font-family: 'Cinzel', serif; transition: 0.4s; margin-top: 20px;
        }
        .submit-btn:hover { background: #af944d; color: #000; }

  /* --- PROFESJONALNE GOTYCKIE NAROŻNIKI --- */
.page-ornament {
    position: fixed;
    width: 180px; /* Większe, by było widać detal */
    height: 180px;
    z-index: 9999;
    pointer-events: none;
    opacity: 0.35; /* Subtelne, by nie zasłaniały treści */
    /* Ten kod poniżej to elegancki, gotycki ornament wektorowy */
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 100 100' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M0 0 L100 0 L100 2 L2 2 L2 100 L0 100 Z M15 15 C 30 5, 45 5, 50 20 C 45 35, 30 35, 15 15 M15 15 C 5 30, 5 45, 20 50 C 35 45, 35 30, 15 15' fill='%23af944d'/%3E%3C/svg%3E");
    background-size: contain;
    background-repeat: no-repeat;
}

/* Pozycjonowanie i obracanie ornamentów w rogach */
.ornament-bl { bottom: 15px; left: 15px; transform: rotate(-90deg); }
.ornament-br { bottom: 15px; right: 15px; transform: rotate(180deg); }

/* Na telefonach muszą zniknąć, bo zasłonią tekst */
@media (max-width: 1100px) {
    .page-ornament { display: none; }
}
    </style>
</head>
<body>

    <nav>
        <div class="nav-container">
            <a href="#" class="nav-home">☥</a>
            <a href="#historia">O nas</a>
            <a href="#ekipa">Artyści</a>
            <a href="#galeria">Galeria</a>
            <a href="#cennik">Cennik</a>
            <a href="#regulamin">Regulamin</a>
            <a href="#newsletter">Zapisy</a>
            <a href="#kontakt">Kontakt</a>
        </div>
    </nav>

    <header style="text-align: center; padding: 120px 30px 60px;">
        <h1 style="font-family: 'Cinzel'; font-size: clamp(3rem, 10vw, 5rem); margin: 0 0 20px 0; letter-spacing: 20px; color: #fff; text-shadow: 0 0 15px rgba(255,255,255,0.1);">MANTRA TATTOO & PIERCING</h1>
        <div class="gothic-divider">✥</div>
        <p style="color:#af944d; letter-spacing:8px; text-transform: uppercase;">Sztuka wpisana w ciało</p>
    </header>

    <section id="historia">
        <h2 data-aos="fade-up">HISTORIA</h2>
        <div class="gothic-divider">♰</div>
        <div style="max-width: 800px; margin: 0 auto; text-align: center; font-size: 1.2rem; font-style: italic;" data-aos="fade-up">
            <p>MANTRA TATTOO & PIERCING powstał w 2026 roku z potrzeby zjednoczenia artystów, dla których tatuaż i piercing to nie tylko rzemiosło, ale rytuał. Nasze progi przekraczają ci, którzy szukają autentyczności, mroku i precyzji w każdym detalu. Stworzyliśmy azyl z dala od zgiełku miasta i masowej kultury. Tutaj czas płynie inaczej. W ciszy i skupieniu, przy akompaniamencie maszyn, zamieniamy Twoje wizje w trwałą sztukę, nie uznając kompromisów w jakości.</p>
        </div>
    </section>

    <section id="ekipa">
        <h2 data-aos="fade-up">ARTYŚCI</h2>
        <div class="gothic-divider">☩</div>
        <div class="team-container">
            <div class="artist-card" data-aos="fade-up">
                <div class="corner top-left"></div><div class="corner top-right"></div>
                <div class="artist-photo"><img src="a1.jpg" alt=""></div>
                <h3>Kornel</h3>
                <p>Blackwork / Dark Art</p>
            </div>
            <div class="artist-card" data-aos="fade-up" data-aos-delay="100">
                <div class="corner top-left"></div><div class="corner top-right"></div>
                <div class="artist-photo"><img src="a2.jpg" alt=""></div>
                <h3>Lidia</h3>
                <p>Ornamental / Dotwork</p>
            </div>
            <div class="artist-card" data-aos="fade-up" data-aos-delay="200">
                <div class="corner top-left"></div><div class="corner top-right"></div>
                <div class="artist-photo"><img src="a3.jpg" alt=""></div>
                <h3>Wiktor</h3>
                <p>Realizm Czarno-Szary</p>
            </div>
            <div class="artist-card" data-aos="fade-up">
                <div class="corner top-left"></div><div class="corner top-right"></div>
                <div class="artist-photo"><img src="a4.jpg" alt=""></div>
                <h3>Blanka</h3>
                <p>Fine Line / Sketch</p>
            </div>
            <div class="artist-card" data-aos="fade-up">
                <div class="corner top-left"></div><div class="corner top-right"></div>
                <div class="artist-photo"><img src="p1.jpg" alt=""></div>
                <h3>Malwina</h3>
                <p>Master Piercer</p>
            </div>
        </div>
    </section>

    <section id="galeria">
        <h2 data-aos="fade-up">GALERIA</h2>
        <div class="gothic-divider">✦</div>
        <div class="gallery-grid">
            <div class="gallery-item" data-aos="zoom-in"><img src="1.jpg" alt=""></div>
            <div class="gallery-item" data-aos="zoom-in" data-aos-delay="50"><img src="2.jpg" alt=""></div>
            <div class="gallery-item" data-aos="zoom-in" data-aos-delay="100"><img src="3.jpg" alt=""></div>
            <div class="gallery-item" data-aos="zoom-in" data-aos-delay="150"><img src="4.jpg" alt=""></div>
            <div class="gallery-item" data-aos="zoom-in" data-aos-delay="200"><img src="5.jpg" alt=""></div>
            <div class="gallery-item" data-aos="zoom-in" data-aos-delay="250"><img src="6.jpg" alt=""></div>
            <div class="gallery-item" data-aos="zoom-in" data-aos-delay="300"><img src="7.jpg" alt=""></div>
            <div class="gallery-item" data-aos="zoom-in" data-aos-delay="350"><img src="8.jpg" alt=""></div>
            <div class="gallery-item" data-aos="zoom-in" data-aos-delay="200"><img src="9.jpg" alt=""></div>
            <div class="gallery-item" data-aos="zoom-in" data-aos-delay="250"><img src="10.jpg" alt=""></div>
            <div class="gallery-item" data-aos="zoom-in" data-aos-delay="300"><img src="11.jpg" alt=""></div>
            <div class="gallery-item" data-aos="zoom-in" data-aos-delay="350"><img src="12.jpg" alt=""></div>
        </div>
    </section>

    <section id="cennik">
        <h2 data-aos="fade-up">CENNIK</h2>
        <div class="gothic-divider">♄</div>
        <div class="swiper mySwiper">
            <div class="swiper-wrapper">
                <div class="swiper-slide">
                    <div class="price-card">
                        <div class="corner top-left"></div><div class="corner top-right"></div>
                        <h3>USZY</h3>
                        <div class="price-item"><span>Lobe</span><span>80-140 zł</span></div>
                        <div class="price-item"><span>Helix</span><span>120-200 zł</span></div>
                        <div class="price-item"><span>Tragus</span><span>140-250 zł</span></div>
                        <div class="price-item"><span>Industrial</span><span>180-250 zł</span></div>
                    </div>
                </div>
                <div class="swiper-slide">
                    <div class="price-card">
                        <div class="corner top-left"></div><div class="corner top-right"></div>
                        <h3>NOS / TWARZ</h3>
                        <div class="price-item"><span>Nostril</span><span>120-200 zł</span></div>
                        <div class="price-item"><span>Septum</span><span>140-260 zł</span></div>
                        <div class="price-item"><span>Medusa</span><span>150-270 zł</span></div>
                        <div class="price-item"><span>Eyebrow</span><span>130-220 zł</span></div>
                    </div>
                </div>
                <div class="swiper-slide">
                    <div class="price-card">
                        <div class="corner top-left"></div><div class="corner top-right"></div>
                        <h3>INTYMNE</h3>
                        <div class="price-item"><span>Christina</span><span>200-350 zł</span></div>
                        <div class="price-item"><span>VCH / HCH</span><span>180-320 zł</span></div>
                        <div class="price-item"><span>Prince Albert</span><span>200-370 zł</span></div>
                    </div>
                </div>
                <div class="swiper-slide">
                    <div class="price-card">
                        <div class="corner top-left"></div><div class="corner top-right"></div>
                        <h3>DODATKI</h3>
                        <div class="price-item"><span>Wymiana</span><span>30-60 zł</span></div>
                        <div class="price-item"><span>Konsultacja</span><span>gratis</span></div>
                        <div class="price-item"><span>Kontrola</span><span>gratis</span></div>
                    </div>
                </div>
            </div>
            <div class="swiper-button-next"></div>
            <div class="swiper-button-prev"></div>
        </div>
    </section>

   <section id="regulamin">
    <h2 data-aos="fade-up" style="font-size: 2.8rem; margin-bottom: 20px;">REGULAMIN</h2>
    <div class="gothic-divider">⚖</div>
    <div style="max-width: 900px; margin: 0 auto; background: rgba(10, 15, 14, 0.9); padding: 60px; border: 1px solid #af944d; position: relative; box-shadow: 0 0 30px rgba(0,0,0,0.8);" data-aos="fade-up">
        
        <div class="corner top-left" style="width: 40px; height: 40px; border-width: 2px;"></div>
        <div class="corner top-right" style="width: 40px; height: 40px; border-width: 2px;"></div>
        <div class="corner bottom-left" style="width: 40px; height: 40px; border-width: 2px;"></div>
        <div class="corner bottom-right" style="width: 40px; height: 40px; border-width: 2px;"></div>
        
        <ul style="list-style: none; padding: 0; text-align: left; font-size: 1.3rem; line-height: 1.8; color: #e3d5b8;">
            <li style="margin-bottom: 25px; border-bottom: 1px solid rgba(175, 148, 77, 0.15); padding-bottom: 15px;">
                <span style="color: #af944d; font-family: 'Cinzel'; font-weight: bold;">✦ Postanowienia Ogólne:</span><br>
                Studio zapewnia najwyższy standard sterylności i higieny. Przystąpienie do zabiegu oznacza pełną akceptację regulaminu oraz pisemne oświadczenie o stanie zdrowia.
            </li>
            
            <li style="margin-bottom: 25px; border-bottom: 1px solid rgba(175, 148, 77, 0.15); padding-bottom: 15px;">
                <span style="color: #af944d; font-family: 'Cinzel'; font-weight: bold;">✦ Wiek i Zgody:</span><br>
                Osoby niepełnoletnie (16+) muszą stawić się z rodzicem lub opiekunem prawnym. Przekłucia intymne oraz modyfikacje zaawansowane wykonujemy wyłącznie osobom pełnoletnim (18+).
            </li>
            
            <li style="margin-bottom: 25px; border-bottom: 1px solid rgba(175, 148, 77, 0.15); padding-bottom: 15px;">
                <span style="color: #af944d; font-family: 'Cinzel'; font-weight: bold;">✦ Rezerwacja:</span><br>
                Rezerwacja terminu wiąże się z wpłatą zadatku. Zadatek jest potwierdzeniem rezerwacji i akceptacją zasad pracy studia.
            </li>

            <li style="margin-bottom: 10px;">
                <span style="color: #af944d; font-family: 'Cinzel'; font-weight: bold;">✦ Bezpieczeństwo:</span><br>
                Obowiązuje całkowity zakaz spożywania alkoholu i środków psychoaktywnych przed wizytą. Studio ma prawo odmówić obsługi osób pod wpływem.
            </li>
        </ul>
    </div>
</section>

    <section id="newsletter" style="text-align: center;">
        <h2 data-aos="fade-up">ZAPISY</h2>
        <div class="gothic-divider">✉</div>
        <div data-aos="fade-up">
            <input type="email" class="newsletter-input" placeholder="WPISZ TWÓJ E-MAIL">
            <br>
            <button class="submit-btn">WYŚLIJ FORMULARZ</button>
        </div>
    </section>

    <section id="kontakt" style="text-align: center; border-top: 1px solid rgba(175,148,77,0.1);">
        <h2 data-aos="fade-up">KONTAKT</h2>
        <p>UL. MISTYCZNA 13, WARSZAWA</p>
        <p>IG: @MANTRA_TATTOO&PIERCING</p>
        <p>TEL: +48 000 000 000</p>
    </section>

    <footer>
        <p style="text-align: center; padding: 50px; opacity: 0.4; font-size: 0.8rem;">© 2026 MANTRA_TATTOO&PIERCING | ALL RIGHTS RESERVED</p>
    </footer>

    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.js"></script>
    <script>
        AOS.init({ duration: 1000, once: true });

        // Karuzela z poprawionym widokiem sąsiednich slajdów
        const swiper = new Swiper(".mySwiper", {
            slidesPerView: 1.2, // Pokazuje kawałek następnego na mobilkach
            centeredSlides: true,
            spaceBetween: 20,
            loop: true,
            navigation: {
                nextEl: ".swiper-button-next",
                prevEl: ".swiper-button-prev",
            },
            breakpoints: {
                768: { slidesPerView: 2 },
                1024: { slidesPerView: 2.5 } // Wyraźnie widać boki "za mgłą"
            }
        });
    </script>
   
<div class="page-ornament ornament-tl"></div>
<div class="page-ornament ornament-tr"></div>
<div class="page-ornament ornament-bl"></div>
<div class="page-ornament ornament-br"></div>
</body>
</html>
