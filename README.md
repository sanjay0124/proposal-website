<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sanju ❤️ Manisha — Forever Yours</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400;1,700&family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Great+Vibes&display=swap" rel="stylesheet">
<style>
*, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

:root {
  --black: #0a0a0a;
  --dark: #111111;
  --dark-red: #3d0000;
  --crimson: #8b0000;
  --red: #dc143c;
  --bright-red: #ff1744;
  --gold: #d4a853;
  --gold-light: #f0d78c;
  --gold-dark: #a07830;
  --rose: #ff6b8a;
  --pink: #ff4081;
}

html { scroll-behavior: smooth; }

body {
  background: var(--black);
  color: #fff;
  font-family: 'Cormorant Garamond', serif;
  overflow-x: hidden;
  min-height: 100vh;
  position: relative;
}

/* Canvas for particles */
#particleCanvas {
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  z-index: 1;
  pointer-events: none;
}

/* Background atmospheric layers */
.bg-layer {
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  z-index: 0;
  overflow: hidden;
}

.bg-layer::before {
  content: '';
  position: absolute;
  top: -50%; left: -50%;
  width: 200%; height: 200%;
  background: radial-gradient(ellipse at 30% 20%, rgba(139, 0, 0, 0.15) 0%, transparent 50%),
              radial-gradient(ellipse at 70% 80%, rgba(139, 0, 0, 0.1) 0%, transparent 50%),
              radial-gradient(ellipse at 50% 50%, rgba(60, 0, 0, 0.2) 0%, transparent 70%);
  animation: bgDrift 20s ease-in-out infinite alternate;
}

.bg-layer::after {
  content: '';
  position: absolute;
  top: 0; left: 0;
  width: 100%; height: 100%;
  background: radial-gradient(circle at 50% 30%, rgba(212, 168, 83, 0.03) 0%, transparent 60%);
  animation: bgPulse 8s ease-in-out infinite alternate;
}

@keyframes bgDrift {
  0% { transform: translate(0, 0) rotate(0deg); }
  100% { transform: translate(-5%, 3%) rotate(3deg); }
}

@keyframes bgPulse {
  0% { opacity: 0.5; }
  100% { opacity: 1; }
}

/* Cinematic blur orbs */
.blur-orb {
  position: fixed;
  border-radius: 50%;
  filter: blur(80px);
  z-index: 0;
  pointer-events: none;
}

.blur-orb-1 {
  width: 400px; height: 400px;
  background: rgba(139, 0, 0, 0.2);
  top: -100px; left: -100px;
  animation: orbFloat1 15s ease-in-out infinite;
}

.blur-orb-2 {
  width: 300px; height: 300px;
  background: rgba(212, 168, 83, 0.08);
  bottom: -50px; right: -50px;
  animation: orbFloat2 18s ease-in-out infinite;
}

.blur-orb-3 {
  width: 250px; height: 250px;
  background: rgba(220, 20, 60, 0.12);
  top: 40%; left: 60%;
  animation: orbFloat3 12s ease-in-out infinite;
}

@keyframes orbFloat1 {
  0%, 100% { transform: translate(0, 0); }
  50% { transform: translate(80px, 60px); }
}

@keyframes orbFloat2 {
  0%, 100% { transform: translate(0, 0); }
  50% { transform: translate(-60px, -80px); }
}

@keyframes orbFloat3 {
  0%, 100% { transform: translate(0, 0) scale(1); }
  50% { transform: translate(-40px, 30px) scale(1.2); }
}

/* Main content wrapper */
.main-wrapper {
  position: relative;
  z-index: 2;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  padding: 40px 20px;
  text-align: center;
}

/* Decorative top line */
.decorative-line {
  width: 120px;
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--gold), transparent);
  margin-bottom: 30px;
  animation: lineGlow 3s ease-in-out infinite;
}

@keyframes lineGlow {
  0%, 100% { opacity: 0.5; width: 120px; }
  50% { opacity: 1; width: 160px; }
}

/* Names heading */
.names-heading {
  font-family: 'Great Vibes', cursive;
  font-size: clamp(2.8rem, 8vw, 5.5rem);
  line-height: 1.2;
  margin-bottom: 10px;
  background: linear-gradient(135deg, var(--gold-light) 0%, var(--gold) 30%, var(--gold-dark) 60%, var(--gold-light) 100%);
  background-size: 200% 200%;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  animation: goldShimmer 4s ease-in-out infinite;
  filter: drop-shadow(0 0 20px rgba(212, 168, 83, 0.3));
  letter-spacing: 2px;
}

@keyframes goldShimmer {
  0%, 100% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
}

/* Subtitle under names */
.subtitle {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(0.9rem, 2.5vw, 1.2rem);
  font-weight: 300;
  font-style: italic;
  color: rgba(212, 168, 83, 0.6);
  letter-spacing: 6px;
  text-transform: uppercase;
  margin-bottom: 50px;
  opacity: 0;
  animation: fadeUp 1.5s ease 0.5s forwards;
}

@keyframes fadeUp {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}

/* Neon heart outline */
.neon-heart-container {
  position: relative;
  width: 160px;
  height: 160px;
  margin: 20px auto 40px;
  opacity: 0;
  animation: fadeScaleIn 1.5s ease 0.8s forwards;
}

@keyframes fadeScaleIn {
  from { opacity: 0; transform: scale(0.5); }
  to { opacity: 1; transform: scale(1); }
}

.neon-heart {
  width: 100%;
  height: 100%;
  filter: drop-shadow(0 0 15px rgba(255, 23, 68, 0.6))
          drop-shadow(0 0 30px rgba(255, 23, 68, 0.4))
          drop-shadow(0 0 60px rgba(255, 23, 68, 0.2));
  animation: neonPulse 2s ease-in-out infinite;
}

.neon-heart svg {
  width: 100%;
  height: 100%;
}

.neon-heart svg path {
  fill: none;
  stroke: var(--bright-red);
  stroke-width: 2;
  stroke-dasharray: 600;
  stroke-dashoffset: 600;
  animation: drawHeart 2.5s ease 1.2s forwards;
}

@keyframes drawHeart {
  to { stroke-dashoffset: 0; }
}

@keyframes neonPulse {
  0%, 100% { filter: drop-shadow(0 0 15px rgba(255, 23, 68, 0.6)) drop-shadow(0 0 30px rgba(255, 23, 68, 0.4)) drop-shadow(0 0 60px rgba(255, 23, 68, 0.2)); }
  50% { filter: drop-shadow(0 0 25px rgba(255, 23, 68, 0.8)) drop-shadow(0 0 50px rgba(255, 23, 68, 0.5)) drop-shadow(0 0 80px rgba(255, 23, 68, 0.3)); }
}

/* Inner glow of heart */
.neon-heart-inner {
  position: absolute;
  top: 50%; left: 50%;
  transform: translate(-50%, -50%);
  width: 80px; height: 80px;
  background: radial-gradient(circle, rgba(255, 23, 68, 0.3) 0%, transparent 70%);
  border-radius: 50%;
  animation: innerGlow 2s ease-in-out infinite;
}

@keyframes innerGlow {
  0%, 100% { opacity: 0.5; transform: translate(-50%, -50%) scale(1); }
  50% { opacity: 1; transform: translate(-50%, -50%) scale(1.3); }
}

/* Main proposal text */
.proposal-text {
  font-family: 'Playfair Display', serif;
  font-size: clamp(1.8rem, 6vw, 3.5rem);
  font-weight: 700;
  line-height: 1.3;
  margin-bottom: 20px;
  opacity: 0;
  animation: fadeUp 1.5s ease 1.5s forwards;
}

.proposal-text .glow {
  color: #fff;
  text-shadow: 0 0 20px rgba(255, 23, 68, 0.5),
               0 0 40px rgba(255, 23, 68, 0.3),
               0 0 80px rgba(255, 23, 68, 0.15);
  animation: textGlow 3s ease-in-out infinite;
}

.proposal-text .heart-emoji {
  display: inline-block;
  animation: heartBeat 1.2s ease-in-out infinite;
  filter: drop-shadow(0 0 10px rgba(255, 23, 68, 0.8));
}

@keyframes textGlow {
  0%, 100% { text-shadow: 0 0 20px rgba(255, 23, 68, 0.5), 0 0 40px rgba(255, 23, 68, 0.3), 0 0 80px rgba(255, 23, 68, 0.15); }
  50% { text-shadow: 0 0 30px rgba(255, 23, 68, 0.7), 0 0 60px rgba(255, 23, 68, 0.4), 0 0 100px rgba(255, 23, 68, 0.2); }
}

@keyframes heartBeat {
  0%, 100% { transform: scale(1); }
  15% { transform: scale(1.25); }
  30% { transform: scale(1); }
  45% { transform: scale(1.15); }
  60% { transform: scale(1); }
}

/* Romantic quote */
.romantic-quote {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(1rem, 3vw, 1.4rem);
  font-weight: 300;
  font-style: italic;
  color: rgba(255, 255, 255, 0.7);
  max-width: 500px;
  margin: 0 auto 50px;
  line-height: 1.8;
  opacity: 0;
  animation: fadeUp 1.5s ease 2s forwards;
}

.romantic-quote .quote-heart {
  display: inline-block;
  color: var(--red);
  filter: drop-shadow(0 0 8px rgba(220, 20, 60, 0.6));
  animation: heartBeat 1.5s ease-in-out infinite;
}

/* Rose decorations */
.roses-container {
  display: flex;
  justify-content: center;
  gap: 30px;
  margin-bottom: 40px;
  opacity: 0;
  animation: fadeUp 1.5s ease 2.3s forwards;
}

.rose {
  font-size: 2rem;
  display: inline-block;
  animation: roseFloat 4s ease-in-out infinite;
  filter: drop-shadow(0 0 10px rgba(139, 0, 0, 0.5));
}

.rose:nth-child(1) { animation-delay: 0s; }
.rose:nth-child(2) { animation-delay: 0.5s; }
.rose:nth-child(3) { animation-delay: 1s; }

@keyframes roseFloat {
  0%, 100% { transform: translateY(0) rotate(-5deg); }
  50% { transform: translateY(-10px) rotate(5deg); }
}

/* Buttons container */
.buttons-container {
  display: flex;
  flex-direction: column;
  gap: 16px;
  align-items: center;
  opacity: 0;
  animation: fadeUp 1.5s ease 2.6s forwards;
}

/* Luxury button base */
.luxury-btn {
  position: relative;
  padding: 16px 48px;
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(1rem, 2.5vw, 1.25rem);
  font-weight: 600;
  letter-spacing: 3px;
  text-transform: uppercase;
  border: none;
  cursor: pointer;
  overflow: hidden;
  transition: all 0.4s ease;
  min-width: 240px;
}

.luxury-btn::before {
  content: '';
  position: absolute;
  top: 0; left: -100%;
  width: 100%; height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255,255,255,0.15), transparent);
  transition: left 0.6s ease;
}

.luxury-btn:hover::before {
  left: 100%;
}

/* Yes button */
.btn-yes {
  background: linear-gradient(135deg, var(--crimson) 0%, var(--red) 50%, var(--crimson) 100%);
  background-size: 200% 200%;
  color: #fff;
  border: 1px solid rgba(255, 23, 68, 0.3);
  box-shadow: 0 0 20px rgba(220, 20, 60, 0.3),
              0 0 40px rgba(220, 20, 60, 0.15),
              inset 0 1px 0 rgba(255,255,255,0.1);
  animation: btnGlow 3s ease-in-out infinite;
}

.btn-yes:hover {
  background-position: 100% 50%;
  box-shadow: 0 0 30px rgba(220, 20, 60, 0.5),
              0 0 60px rgba(220, 20, 60, 0.25),
              inset 0 1px 0 rgba(255,255,255,0.2);
  transform: translateY(-2px) scale(1.02);
}

@keyframes btnGlow {
  0%, 100% { box-shadow: 0 0 20px rgba(220, 20, 60, 0.3), 0 0 40px rgba(220, 20, 60, 0.15), inset 0 1px 0 rgba(255,255,255,0.1); }
  50% { box-shadow: 0 0 30px rgba(220, 20, 60, 0.4), 0 0 60px rgba(220, 20, 60, 0.2), inset 0 1px 0 rgba(255,255,255,0.15); }
}

/* Forever button */
.btn-forever {
  background: transparent;
  color: var(--gold);
  border: 1px solid var(--gold-dark);
  box-shadow: 0 0 15px rgba(212, 168, 83, 0.1),
              inset 0 0 15px rgba(212, 168, 83, 0.05);
  animation: btnGoldGlow 3s ease-in-out infinite;
}

.btn-forever:hover {
  background: rgba(212, 168, 83, 0.1);
  border-color: var(--gold);
  box-shadow: 0 0 25px rgba(212, 168, 83, 0.2),
              0 0 50px rgba(212, 168, 83, 0.1),
              inset 0 0 20px rgba(212, 168, 83, 0.08);
  transform: translateY(-2px) scale(1.02);
}

@keyframes btnGoldGlow {
  0%, 100% { box-shadow: 0 0 15px rgba(212, 168, 83, 0.1), inset 0 0 15px rgba(212, 168, 83, 0.05); }
  50% { box-shadow: 0 0 25px rgba(212, 168, 83, 0.15), inset 0 0 20px rgba(212, 168, 83, 0.08); }
}

/* Floating hearts */
.floating-hearts {
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  pointer-events: none;
  z-index: 1;
  overflow: hidden;
}

.float-heart {
  position: absolute;
  bottom: -60px;
  font-size: 1.2rem;
  opacity: 0;
  animation: floatUp linear infinite;
  filter: drop-shadow(0 0 6px rgba(255, 23, 68, 0.5));
}

@keyframes floatUp {
  0% { opacity: 0; transform: translateY(0) translateX(0) rotate(0deg) scale(0.5); }
  10% { opacity: 0.8; }
  90% { opacity: 0.6; }
  100% { opacity: 0; transform: translateY(-110vh) translateX(40px) rotate(360deg) scale(1); }
}

/* Bottom decorative line */
.bottom-line {
  width: 80px;
  height: 1px;
  background: linear-gradient(90deg, transparent, rgba(212, 168, 83, 0.4), transparent);
  margin-top: 50px;
  opacity: 0;
  animation: fadeUp 1.5s ease 3s forwards;
}

.bottom-text {
  font-family: 'Cormorant Garamond', serif;
  font-size: 0.75rem;
  color: rgba(212, 168, 83, 0.3);
  letter-spacing: 4px;
  text-transform: uppercase;
  margin-top: 15px;
  opacity: 0;
  animation: fadeUp 1.5s ease 3.2s forwards;
}

/* Celebration overlay */
.celebration-overlay {
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  z-index: 100;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background: rgba(10, 10, 10, 0.95);
  opacity: 0;
  visibility: hidden;
  transition: all 0.8s ease;
  backdrop-filter: blur(20px);
}

.celebration-overlay.active {
  opacity: 1;
  visibility: visible;
}

.celebration-text {
  font-family: 'Great Vibes', cursive;
  font-size: clamp(2.5rem, 8vw, 5rem);
  background: linear-gradient(135deg, var(--gold-light), var(--gold), var(--gold-light));
  background-size: 200% 200%;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  animation: goldShimmer 3s ease-in-out infinite;
  text-align: center;
  filter: drop-shadow(0 0 30px rgba(212, 168, 83, 0.4));
  transform: scale(0.5);
  transition: transform 0.8s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.celebration-overlay.active .celebration-text {
  transform: scale(1);
}

.celebration-sub {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(1rem, 3vw, 1.4rem);
  font-style: italic;
  color: rgba(255, 255, 255, 0.7);
  margin-top: 20px;
  opacity: 0;
  transition: opacity 0.8s ease 0.5s;
}

.celebration-overlay.active .celebration-sub {
  opacity: 1;
}

.celebration-hearts {
  font-size: 2.5rem;
  margin-top: 30px;
  opacity: 0;
  transition: opacity 0.8s ease 0.8s;
}

.celebration-overlay.active .celebration-hearts {
  opacity: 1;
}

.celebration-hearts span {
  display: inline-block;
  animation: heartBeat 1.2s ease-in-out infinite;
  filter: drop-shadow(0 0 15px rgba(255, 23, 68, 0.8));
}

.celebration-hearts span:nth-child(2) { animation-delay: 0.2s; }
.celebration-hearts span:nth-child(3) { animation-delay: 0.4s; }

.close-celebration {
  margin-top: 40px;
  padding: 10px 30px;
  font-family: 'Cormorant Garamond', serif;
  font-size: 0.9rem;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: rgba(212, 168, 83, 0.6);
  background: transparent;
  border: 1px solid rgba(212, 168, 83, 0.2);
  cursor: pointer;
  opacity: 0;
  transition: all 0.4s ease, opacity 0.8s ease 1.2s;
}

.celebration-overlay.active .close-celebration {
  opacity: 1;
}

.close-celebration:hover {
  color: var(--gold);
  border-color: var(--gold);
  background: rgba(212, 168, 83, 0.1);
}

/* Celebration canvas */
#celebrationCanvas {
  position: absolute;
  top: 0; left: 0;
  width: 100%; height: 100%;
  pointer-events: none;
}

/* Vignette */
.vignette {
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  background: radial-gradient(ellipse at center, transparent 40%, rgba(0,0,0,0.7) 100%);
  z-index: 1;
  pointer-events: none;
}

/* Corner decorations */
.corner-deco {
  position: fixed;
  width: 80px;
  height: 80px;
  z-index: 2;
  opacity: 0.15;
  pointer-events: none;
}

.corner-deco svg {
  width: 100%;
  height: 100%;
}

.corner-tl { top: 20px; left: 20px; }
.corner-tr { top: 20px; right: 20px; transform: scaleX(-1); }
.corner-bl { bottom: 20px; left: 20px; transform: scaleY(-1); }
.corner-br { bottom: 20px; right: 20px; transform: scale(-1, -1); }

/* Scroll indicator */
.scroll-hint {
  position: fixed;
  bottom: 30px;
  left: 50%;
  transform: translateX(-50%);
  z-index: 3;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
  opacity: 0;
  animation: fadeUp 1.5s ease 3.5s forwards;
}

.scroll-hint span {
  font-family: 'Cormorant Garamond', serif;
  font-size: 0.65rem;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: rgba(212, 168, 83, 0.3);
}

.scroll-arrow {
  width: 20px;
  height: 20px;
  border-right: 1px solid rgba(212, 168, 83, 0.3);
  border-bottom: 1px solid rgba(212, 168, 83, 0.3);
  transform: rotate(45deg);
  animation: scrollBounce 2s ease-in-out infinite;
}

@keyframes scrollBounce {
  0%, 100% { transform: rotate(45deg) translate(0, 0); opacity: 0.3; }
  50% { transform: rotate(45deg) translate(5px, 5px); opacity: 0.7; }
}

/* Second section */
.second-section {
  position: relative;
  z-index: 2;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 80px 20px;
  text-align: center;
}

.love-letter {
  max-width: 600px;
  padding: 50px 40px;
  border: 1px solid rgba(212, 168, 83, 0.15);
  background: rgba(17, 17, 17, 0.8);
  backdrop-filter: blur(10px);
  position: relative;
}

.love-letter::before {
  content: '"';
  position: absolute;
  top: -20px; left: 30px;
  font-family: 'Playfair Display', serif;
  font-size: 6rem;
  color: rgba(212, 168, 83, 0.15);
  line-height: 1;
}

.love-letter p {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(1rem, 2.5vw, 1.2rem);
  font-weight: 300;
  line-height: 2;
  color: rgba(255, 255, 255, 0.65);
  margin-bottom: 20px;
}

.love-letter p:last-child {
  margin-bottom: 0;
  font-style: italic;
  color: rgba(212, 168, 83, 0.5);
}

.love-letter .highlight {
  color: var(--rose);
  font-weight: 400;
}

.section-title {
  font-family: 'Great Vibes', cursive;
  font-size: clamp(2rem, 5vw, 3rem);
  background: linear-gradient(135deg, var(--gold-light), var(--gold));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  margin-bottom: 40px;
  filter: drop-shadow(0 0 15px rgba(212, 168, 83, 0.2));
}

/* Fade in on scroll */
.reveal {
  opacity: 0;
  transform: translateY(30px);
  transition: all 1s ease;
}

.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}

/* Third section - timeline */
.timeline-section {
  position: relative;
  z-index: 2;
  padding: 80px 20px 120px;
  text-align: center;
}

.timeline {
  max-width: 500px;
  margin: 0 auto;
  position: relative;
}

.timeline::before {
  content: '';
  position: absolute;
  left: 50%;
  top: 0; bottom: 0;
  width: 1px;
  background: linear-gradient(to bottom, transparent, rgba(212, 168, 83, 0.3), transparent);
  transform: translateX(-50%);
}

.timeline-item {
  position: relative;
  padding: 30px 0;
  opacity: 0;
  transform: translateY(20px);
  transition: all 0.8s ease;
}

.timeline-item.visible {
  opacity: 1;
  transform: translateY(0);
}

.timeline-dot {
  width: 10px;
  height: 10px;
  background: var(--gold);
  border-radius: 50%;
  margin: 0 auto 15px;
  box-shadow: 0 0 15px rgba(212, 168, 83, 0.4);
}

.timeline-item h3 {
  font-family: 'Playfair Display', serif;
  font-size: 1.1rem;
  color: var(--gold-light);
  margin-bottom: 8px;
  font-weight: 400;
}

.timeline-item p {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1rem;
  color: rgba(255, 255, 255, 0.5);
  font-weight: 300;
  line-height: 1.6;
}

/* Music toggle */
.music-toggle {
  position: fixed;
  bottom: 20px;
  right: 20px;
  z-index: 50;
  width: 44px;
  height: 44px;
  border-radius: 50%;
  border: 1px solid rgba(212, 168, 83, 0.2);
  background: rgba(17, 17, 17, 0.8);
  backdrop-filter: blur(10px);
  color: var(--gold);
  font-size: 1.1rem;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.3s ease;
  opacity: 0;
  animation: fadeUp 1s ease 4s forwards;
}

.music-toggle:hover {
  border-color: var(--gold);
  background: rgba(212, 168, 83, 0.1);
  transform: scale(1.1);
}

.music-bars {
  display: flex;
  gap: 2px;
  align-items: flex-end;
  height: 16px;
}

.music-bars span {
  display: block;
  width: 3px;
  background: var(--gold);
  border-radius: 2px;
  transition: height 0.3s ease;
}

.music-bars.playing span:nth-child(1) { animation: musicBar 0.6s ease-in-out infinite alternate; }
.music-bars.playing span:nth-child(2) { animation: musicBar 0.6s ease-in-out 0.2s infinite alternate; }
.music-bars.playing span:nth-child(3) { animation: musicBar 0.6s ease-in-out 0.1s infinite alternate; }
.music-bars.playing span:nth-child(4) { animation: musicBar 0.6s ease-in-out 0.3s infinite alternate; }

.music-bars:not(.playing) span { height: 3px !important; }

@keyframes musicBar {
  from { height: 3px; }
  to { height: 16px; }
}

/* Responsive */
@media (max-width: 640px) {
  .neon-heart-container { width: 120px; height: 120px; }
  .neon-heart-inner { width: 60px; height: 60px; }
  .love-letter { padding: 40px 25px; }
  .corner-deco { width: 50px; height: 50px; }
  .luxury-btn { padding: 14px 36px; min-width: 200px; }
  .roses-container { gap: 20px; }
  .scroll-hint { display: none; }
}

@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
</style>
</head>
<body>

<!-- Background layers -->
<div class="bg-layer"></div>
<div class="blur-orb blur-orb-1"></div>
<div class="blur-orb blur-orb-2"></div>
<div class="blur-orb blur-orb-3"></div>
<div class="vignette"></div>

<!-- Particle canvas -->
<canvas id="particleCanvas"></canvas>

<!-- Floating hearts -->
<div class="floating-hearts" id="floatingHearts"></div>

<!-- Corner decorations -->
<div class="corner-deco corner-tl">
  <svg viewBox="0 0 80 80" fill="none"><path d="M0 0 L30 0 L30 5 L5 5 L5 30 L0 30 Z" fill="url(#cornerGrad)"/><defs><linearGradient id="cornerGrad" x1="0" y1="0" x2="30" y2="30"><stop offset="0%" stop-color="#d4a853"/><stop offset="100%" stop-color="#d4a853" stop-opacity="0"/></linearGradient></defs></svg>
</div>
<div class="corner-deco corner-tr">
  <svg viewBox="0 0 80 80" fill="none"><path d="M0 0 L30 0 L30 5 L5 5 L5 30 L0 30 Z" fill="url(#cornerGrad2)"/><defs><linearGradient id="cornerGrad2" x1="0" y1="0" x2="30" y2="30"><stop offset="0%" stop-color="#d4a853"/><stop offset="100%" stop-color="#d4a853" stop-opacity="0"/></linearGradient></defs></svg>
</div>
<div class="corner-deco corner-bl">
  <svg viewBox="0 0 80 80" fill="none"><path d="M0 0 L30 0 L30 5 L5 5 L5 30 L0 30 Z" fill="url(#cornerGrad3)"/><defs><linearGradient id="cornerGrad3" x1="0" y1="0" x2="30" y2="30"><stop offset="0%" stop-color="#d4a853"/><stop offset="100%" stop-color="#d4a853" stop-opacity="0"/></linearGradient></defs></svg>
</div>
<div class="corner-deco corner-br">
  <svg viewBox="0 0 80 80" fill="none"><path d="M0 0 L30 0 L30 5 L5 5 L5 30 L0 30 Z" fill="url(#cornerGrad4)"/><defs><linearGradient id="cornerGrad4" x1="0" y1="0" x2="30" y2="30"><stop offset="0%" stop-color="#d4a853"/><stop offset="100%" stop-color="#d4a853" stop-opacity="0"/></linearGradient></defs></svg>
</div>

<!-- Main Hero Section -->
<section class="main-wrapper">
  <div class="decorative-line"></div>

  <h1 class="names-heading">Sanju ❤️ Manisha</h1>
  <p class="subtitle">A love story written in the stars</p>

  <div class="neon-heart-container">
    <div class="neon-heart">
      <svg viewBox="0 0 512 512">
        <path d="M462.3 62.6C407.5 15.9 326 24.3 275.7 76.2L256 96.5l-19.7-20.3C186.1 24.3 104.5 15.9 49.7 62.6c-62.8 53.6-66.1 149.8-9.9 207.9l193.5 199.8c12.5 12.9 32.8 12.9 45.3 0l193.5-199.8c56.3-58.1 53-154.3-9.8-207.9z"/>
      </svg>
    </div>
    <div class="neon-heart-inner"></div>
  </div>

  <h2 class="proposal-text">
    <span class="glow">Will You Be Mine Forever?</span>
    <span class="heart-emoji">❤️</span>
  </h2>

  <p class="romantic-quote">
    You are my today and all of my tomorrows <span class="quote-heart">❤️</span>
  </p>

  <div class="roses-container">
    <span class="rose">🌹</span>
    <span class="rose">🌹</span>
    <span class="rose">🌹</span>
  </div>

  <div class="buttons-container">
    <button class="luxury-btn btn-yes" onclick="showCelebration()">Yes ❤️</button>
    <button class="luxury-btn btn-forever" onclick="showCelebration()">Forever Yours ❤️</button>
  </div>

  <div class="bottom-line"></div>
  <p class="bottom-text">With all my love</p>
</section>

<!-- Second Section - Love Letter -->
<section class="second-section">
  <h2 class="section-title reveal">My Dearest Manisha</h2>
  <div class="love-letter reveal">
    <p>
      From the moment you walked into my life, everything changed. The world that was once painted in shades of grey suddenly burst into <span class="highlight">crimson and gold</span>, every sunset reminded me of your warmth, and every heartbeat echoed your name.
    </p>
    <p>
      You are the <span class="highlight">poetry I never knew how to write</span>, the melody that plays in my silence, and the dream I never want to wake from. With you, I have found not just love, but a home for my soul.
    </p>
    <p>
      — Forever & always, Sanju ❤️
    </p>
  </div>
</section>

<!-- Third Section - Our Story -->
<section class="timeline-section">
  <h2 class="section-title reveal">Our Love Story</h2>
  <div class="timeline">
    <div class="timeline-item reveal">
      <div class="timeline-dot"></div>
      <h3>The First Glance</h3>
      <p>The universe conspired to bring our paths together, and in that single moment, my heart knew what my mind had yet to understand.</p>
    </div>
    <div class="timeline-item reveal">
      <div class="timeline-dot"></div>
      <h3>Falling Deeper</h3>
      <p>Every conversation, every stolen glance, every shared laugh — they all wove a tapestry of love that grew stronger with each passing day.</p>
    </div>
    <div class="timeline-item reveal">
      <div class="timeline-dot"></div>
      <h3>Knowing You're The One</h3>
      <p>There came a moment of absolute clarity — a quiet certainty that you are the one I want beside me for every sunrise and every starlit night.</p>
    </div>
    <div class="timeline-item reveal">
      <div class="timeline-dot"></div>
      <h3>This Promise</h3>
      <p>Today, I ask you not just for your hand, but for your forever. To build a life painted in love, laughter, and endless devotion.</p>
    </div>
  </div>
</section>

<!-- Scroll hint -->
<div class="scroll-hint">
  <span>Scroll</span>
  <div class="scroll-arrow"></div>
</div>

<!-- Music toggle -->
<button class="music-toggle" id="musicToggle" onclick="toggleMusic()" aria-label="Toggle ambient music">
  <div class="music-bars" id="musicBars">
    <span style="height:3px"></span>
    <span style="height:3px"></span>
    <span style="height:3px"></span>
    <span style="height:3px"></span>
  </div>
</button>

<!-- Celebration Overlay -->
<div class="celebration-overlay" id="celebrationOverlay">
  <canvas id="celebrationCanvas"></canvas>
  <div class="celebration-text">She Said Yes!</div>
  <p class="celebration-sub">Sanju & Manisha — Forever begins now</p>
  <div class="celebration-hearts">
    <span>❤️</span>
    <span>💕</span>
    <span>❤️</span>
  </div>
  <button class="close-celebration" onclick="closeCelebration()">Close</button>
</div>

<script>
// ========== PARTICLE SYSTEM ==========
const canvas = document.getElementById('particleCanvas');
const ctx = canvas.getContext('2d');
let particles = [];
let animationId;

function resizeCanvas() {
  canvas.width = window.innerWidth;
  canvas.height = window.innerHeight;
}
resizeCanvas();
window.addEventListener('resize', resizeCanvas);

class Particle {
  constructor() {
    this.reset();
  }
  reset() {
    this.x = Math.random() * canvas.width;
    this.y = Math.random() * canvas.height;
    this.size = Math.random() * 2 + 0.5;
    this.speedX = (Math.random() - 0.5) * 0.3;
    this.speedY = (Math.random() - 0.5) * 0.3;
    this.opacity = Math.random() * 0.5 + 0.1;
    this.opacitySpeed = (Math.random() - 0.5) * 0.005;
    this.color = Math.random() > 0.7 
      ? `rgba(212, 168, 83, ${this.opacity})`
      : Math.random() > 0.5
        ? `rgba(220, 20, 60, ${this.opacity})`
        : `rgba(255, 255, 255, ${this.opacity})`;
  }
  update() {
    this.x += this.speedX;
    this.y += this.speedY;
    this.opacity += this.opacitySpeed;
    if (this.opacity <= 0.05 || this.opacity >= 0.6) this.opacitySpeed *= -1;
    if (this.x < 0 || this.x > canvas.width || this.y < 0 || this.y > canvas.height) this.reset();
  }
  draw() {
    ctx.beginPath();
    ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
    ctx.fillStyle = this.color;
    ctx.fill();
    // Glow
    ctx.beginPath();
    ctx.arc(this.x, this.y, this.size * 3, 0, Math.PI * 2);
    const grad = ctx.createRadialGradient(this.x, this.y, 0, this.x, this.y, this.size * 3);
    grad.addColorStop(0, this.color);
    grad.addColorStop(1, 'rgba(0,0,0,0)');
    ctx.fillStyle = grad;
    ctx.fill();
  }
}

const particleCount = Math.min(80, Math.floor(window.innerWidth * window.innerHeight / 15000));
for (let i = 0; i < particleCount; i++) {
  particles.push(new Particle());
}

function animateParticles() {
  ctx.clearRect(0, 0, canvas.width, canvas.height);
  particles.forEach(p => { p.update(); p.draw(); });
  animationId = requestAnimationFrame(animateParticles);
}
animateParticles();

// ========== FLOATING HEARTS ==========
const heartsContainer = document.getElementById('floatingHearts');
const heartEmojis = ['❤️', '💕', '💖', '💗', '🌹', '❤️‍🔥'];

function createFloatingHeart() {
  const heart = document.createElement('div');
  heart.className = 'float-heart';
  heart.textContent = heartEmojis[Math.floor(Math.random() * heartEmojis.length)];
  heart.style.left = Math.random() * 100 + '%';
  heart.style.fontSize = (Math.random() * 1 + 0.8) + 'rem';
  heart.style.animationDuration = (Math.random() * 8 + 8) + 's';
  heart.style.animationDelay = Math.random() * 2 + 's';
  heartsContainer.appendChild(heart);
  setTimeout(() => heart.remove(), 18000);
}

setInterval(createFloatingHeart, 2000);
for (let i = 0; i < 5; i++) setTimeout(createFloatingHeart, i * 400);

// ========== SCROLL REVEAL ==========
const revealElements = document.querySelectorAll('.reveal');
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('visible');
    }
  });
}, { threshold: 0.2, rootMargin: '0px 0px -50px 0px' });

revealElements.forEach(el => observer.observe(el));

// Hide scroll hint on scroll
window.addEventListener('scroll', () => {
  const hint = document.querySelector('.scroll-hint');
  if (hint && window.scrollY > 100) {
    hint.style.opacity = '0';
    hint.style.transition = 'opacity 0.5s ease';
  }
});

// ========== CELEBRATION ==========
const overlay = document.getElementById('celebrationOverlay');
const celebCanvas = document.getElementById('celebrationCanvas');
const celebCtx = celebCanvas.getContext('2d');
let celebParticles = [];
let celebAnimId;
let celebActive = false;

function resizeCelebCanvas() {
  celebCanvas.width = window.innerWidth;
  celebCanvas.height = window.innerHeight;
}

class CelebParticle {
  constructor() {
    this.x = Math.random() * celebCanvas.width;
    this.y = -20;
    this.size = Math.random() * 6 + 3;
    this.speedX = (Math.random() - 0.5) * 4;
    this.speedY = Math.random() * 3 + 2;
    this.rotation = Math.random() * 360;
    this.rotSpeed = (Math.random() - 0.5) * 10;
    this.opacity = 1;
    const colors = ['#d4a853', '#f0d78c', '#dc143c', '#ff1744', '#ff6b8a', '#fff'];
    this.color = colors[Math.floor(Math.random() * colors.length)];
    this.shape = Math.random() > 0.5 ? 'rect' : 'circle';
  }
  update() {
    this.x += this.speedX;
    this.y += this.speedY;
    this.speedY += 0.05;
    this.rotation += this.rotSpeed;
    if (this.y > celebCanvas.height - 100) this.opacity -= 0.02;
  }
  draw() {
    celebCtx.save();
    celebCtx.translate(this.x, this.y);
    celebCtx.rotate((this.rotation * Math.PI) / 180);
    celebCtx.globalAlpha = Math.max(0, this.opacity);
    celebCtx.fillStyle = this.color;
    if (this.shape === 'rect') {
      celebCtx.fillRect(-this.size / 2, -this.size / 2, this.size, this.size * 0.6);
    } else {
      celebCtx.beginPath();
      celebCtx.arc(0, 0, this.size / 2, 0, Math.PI * 2);
      celebCtx.fill();
    }
    celebCtx.restore();
  }
}

function animateCelebration() {
  if (!celebActive) return;
  celebCtx.clearRect(0, 0, celebCanvas.width, celebCanvas.height);
  if (Math.random() > 0.7) celebParticles.push(new CelebParticle());
  celebParticles = celebParticles.filter(p => p.opacity > 0);
  celebParticles.forEach(p => { p.update(); p.draw(); });
  celebAnimId = requestAnimationFrame(animateCelebration);
}

function showCelebration() {
  resizeCelebCanvas();
  overlay.classList.add('active');
  celebActive = true;
  celebParticles = [];
  animateCelebration();
  // Burst of particles
  for (let i = 0; i < 80; i++) {
    const p = new CelebParticle();
    p.y = Math.random() * celebCanvas.height * 0.5;
    p.speedY = Math.random() * 2 + 1;
    celebParticles.push(p);
  }
}

function closeCelebration() {
  overlay.classList.remove('active');
  celebActive = false;
  if (celebAnimId) cancelAnimationFrame(celebAnimId);
  celebCtx.clearRect(0, 0, celebCanvas.width, celebCanvas.height);
  celebParticles = [];
}

// ========== AMBIENT MUSIC (Web Audio API) ==========
let audioCtx = null;
let isPlaying = false;
let gainNode = null;
let oscillators = [];

function createAmbientMusic() {
  audioCtx = new (window.AudioContext || window.webkitAudioContext)();
  gainNode = audioCtx.createGain();
  gainNode.gain.value = 0;
  gainNode.connect(audioCtx.destination);

  const notes = [
    { freq: 130.81, type: 'sine' },    // C3
    { freq: 164.81, type: 'sine' },    // E3
    { freq: 196.00, type: 'sine' },    // G3
    { freq: 246.94, type: 'triangle' }, // B3
    { freq: 261.63, type: 'sine' },    // C4
  ];

  notes.forEach((note, i) => {
    const osc = audioCtx.createOscillator();
    const oscGain = audioCtx.createGain();
    osc.type = note.type;
    osc.frequency.value = note.freq;
    oscGain.gain.value = 0.04 - i * 0.005;
    osc.connect(oscGain);
    oscGain.connect(gainNode);
    osc.start();
    oscillators.push({ osc, gain: oscGain });

    // Gentle frequency modulation
    const lfo = audioCtx.createOscillator();
    const lfoGain = audioCtx.createGain();
    lfo.frequency.value = 0.1 + i * 0.05;
    lfoGain.gain.value = note.freq * 0.002;
    lfo.connect(lfoGain);
    lfoGain.connect(osc.frequency);
    lfo.start();
  });
}

function toggleMusic() {
  const bars = document.getElementById('musicBars');
  if (!audioCtx) createAmbientMusic();

  if (!isPlaying) {
    audioCtx.resume();
    gainNode.gain.linearRampToValueAtTime(0.3, audioCtx.currentTime + 1);
    bars.classList.add('playing');
    isPlaying = true;
  } else {
    gainNode.gain.linearRampToValueAtTime(0, audioCtx.currentTime + 0.5);
    bars.classList.remove('playing');
    isPlaying = false;
  }
}

// ========== MOUSE INTERACTION - SPARKLE TRAIL ==========
let mouseX = 0, mouseY = 0;
let sparkles = [];

document.addEventListener('mousemove', (e) => {
  mouseX = e.clientX;
  mouseY = e.clientY;
  if (Math.random() > 0.6) {
    sparkles.push({
      x: mouseX,
      y: mouseY,
      size: Math.random() * 3 + 1,
      opacity: 0.8,
      decay: 0.02 + Math.random() * 0.02,
      color: Math.random() > 0.5 ? '#d4a853' : '#dc143c'
    });
  }
});

function drawSparkles() {
  sparkles.forEach((s, i) => {
    s.opacity -= s.decay;
    s.size *= 0.97;
    if (s.opacity <= 0) { sparkles.splice(i, 1); return; }
    ctx.save();
    ctx.globalAlpha = s.opacity;
    ctx.fillStyle = s.color;
    ctx.beginPath();
    ctx.arc(s.x, s.y, s.size, 0, Math.PI * 2);
    ctx.fill();
    // Glow
    const g = ctx.createRadialGradient(s.x, s.y, 0, s.x, s.y, s.size * 4);
    g.addColorStop(0, s.color);
    g.addColorStop(1, 'rgba(0,0,0,0)');
    ctx.fillStyle = g;
    ctx.globalAlpha = s.opacity * 0.3;
    ctx.beginPath();
    ctx.arc(s.x, s.y, s.size * 4, 0, Math.PI * 2);
    ctx.fill();
    ctx.restore();
  });
  requestAnimationFrame(drawSparkles);
}
drawSparkles();

// ========== RESIZE HANDLER ==========
window.addEventListener('resize', () => {
  if (celebActive) resizeCelebCanvas();
});
</script>
</body>
</html>
