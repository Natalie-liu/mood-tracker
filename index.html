@tailwind base;
@tailwind components;
@tailwind utilities;
import React, { useState } from 'react';
import { motion, AnimatePresence } from 'framer-motion';
import { MOOD_HIERARCHY, PROMPTS, saveMoodLog } from './logistics';

export default function MainApp() {
  const [view, setView] = useState('selector'); // selector, reflection, patterns
  const [step, setStep] = useState(1); // 1: Core, 2: Secondary, 3: Tertiary
  const [selection, setSelection] = useState({ core: '', secondary: '', tertiary: '' });
  const [note, setNote] = useState('');

  // 1. Logic for picking moods
  const handleSelection = (level, value) => {
    setSelection(prev => ({ ...prev, [level]: value }));
    if (level === 'tertiary') {
      setView('reflection');
    } else {
      setStep(step + 1);
    }
  };

  return (
    <div className="app-container p-6 max-w-lg mx-auto text-center">
      <AnimatePresence mode="wait">
        
        {/* VIEW: MOOD SELECTOR */}
        {view === 'selector' && (
          <motion.div key="selector" initial={{opacity:0}} animate={{opacity:1}} exit={{opacity:0}}>
            <h1 className="text-3xl font-light mb-10">How do you feel?</h1>
            
            <div className="grid gap-4">
              {/* Step 1: Core */}
              {step === 1 && Object.keys(MOOD_HIERARCHY).map(m => (
                <button key={m} onClick={() => handleSelection('core', m)} className="p-5 rounded-2xl border hover:bg-slate-50">
                  {m}
                </button>
              ))}

              {/* Step 2: Secondary */}
              {step === 2 && Object.keys(MOOD_HIERARCHY[selection.core].secondary).map(m => (
                <button key={m} onClick={() => handleSelection('secondary', m)} className="p-5 rounded-2xl border bg-slate-50">
                  {m}
                </button>
              ))}

              {/* Step 3: Tertiary (Nuance) */}
              {step === 3 && MOOD_HIERARCHY[selection.core].secondary[selection.secondary].map(m => (
                <button key={m} onClick={() => handleSelection('tertiary', m)} className="p-5 rounded-2xl border bg-blue-50">
                  {m}
                </button>
              ))}
            </div>
          </motion.div>
        )}

        {/* VIEW: REFLECTION */}
        {view === 'reflection' && (
          <motion.div key="reflection" initial={{y: 20}} animate={{y: 0}}>
            <h2 className="text-sm uppercase tracking-widest opacity-50 mb-2">Reflect</h2>
            <p className="text-xl mb-6 font-serif italic text-slate-700">"{PROMPTS[0]}"</p>
            
            <textarea 
              value={note}
              onChange={(e) => setNote(e.target.value)}
              className="w-full h-40 p-4 bg-white rounded-3xl border-none shadow-inner focus:ring-2 focus:ring-blue-100"
              placeholder="Start writing..."
            />

            <button 
              onClick={() => {
                saveMoodLog({ ...selection, note });
                setView('success');
              }}
              className="mt-8 px-10 py-4 bg-slate-800 text-white rounded-full"
            >
              Save Entry
            </button>
          </motion.div>
        )}

        {/* VIEW: SUCCESS */}
        {view === 'success' && (
          <motion.div key="success" className="py-20">
            <h2 className="text-2xl font-light mb-4">Logged.</h2>
            <p className="opacity-60 mb-8">Take a deep breath.</p>
            <button onClick={() => { setView('selector'); setStep(1); }} className="underline">Back home</button>
          </motion.div>
        )}

      </AnimatePresence>
    </div>
  );
}
:root {
  --bg-color: #fdfcfb;
  --card-bg: #ffffff;
  --text-main: #4a4e69;
  --accent: #9eb3c2;
  --button-hover: #8d99ae;
}

.theme-forest {
  --bg-color: #f1f3f0;
  --card-bg: #ffffff;
  --text-main: #2d3319;
  --accent: #798478;
  --button-hover: #4e5340;
}

.theme-midnight {
  --bg-color: #1a1a2e;
  --card-bg: #16213e;
  --text-main: #e94560;
  --accent: #0f3460;
  --button-hover: #533483;
}

body {
  background-color: var(--bg-color);
  color: var(--text-main);
  transition: all 0.5s ease;
}
import React, { useState, useEffect } from 'react';
import { motion, AnimatePresence } from 'framer-motion';
import { MOOD_HIERARCHY, PROMPTS, saveMoodLog, getAllLogs, THEMES, MOOD_COLORS } from './logistics';

export default function MainApp() {
  const [view, setView] = useState('selector'); // selector, reflection, patterns
  const [theme, setTheme] = useState(THEMES.soft);
  const [logs, setLogs] = useState([]);

  // Load logs on mount
  useEffect(() => {
    setLogs(getAllLogs());
  }, [view]);

  // Apply theme variables to the document
  useEffect(() => {
    document.documentElement.style.setProperty('--bg-color', theme.bg);
    document.documentElement.style.setProperty('--text-main', theme.text);
    document.documentElement.style.setProperty('--accent', theme.accent);
  }, [theme]);

  return (
    <div className="min-h-screen transition-colors duration-1000" style={{ backgroundColor: 'var(--bg-color)', color: 'var(--text-main)' }}>
      
      {/* Top Nav: Theme & View Switcher */}
      <nav className="p-6 flex justify-between items-center max-w-4xl mx-auto">
        <div className="flex gap-4">
          <button onClick={() => setView('selector')} className={`text-sm ${view === 'selector' ? 'font-bold' : 'opacity-50'}`}>Track</button>
          <button onClick={() => setView('patterns')} className={`text-sm ${view === 'patterns' ? 'font-bold' : 'opacity-50'}`}>Patterns</button>
        </div>
        
        <select 
          onChange={(e) => setTheme(THEMES[e.target.value])}
          className="bg-transparent border-none text-sm cursor-pointer opacity-50 focus:ring-0"
        >
          <option value="soft">Soft Cloud</option>
          <option value="forest">Quiet Forest</option>
          <option value="midnight">Midnight</option>
        </select>
      </nav>

      <main className="max-w-lg mx-auto p-6">
        <AnimatePresence mode="wait">
          
          {/* VIEW: LOGGING (from previous step) */}
          {view === 'selector' && (
             <MoodSelectorComponent onComplete={() => setView('patterns')} />
          )}

          {/* VIEW: PATTERNS (The Calendar) */}
          {view === 'patterns' && (
            <motion.div key="patterns" initial={{ opacity: 0 }} animate={{ opacity: 1 }}>
              <header className="mb-10">
                <h2 className="text-3xl font-light">Your Journey</h2>
                <p className="opacity-60">Every color is a step forward.</p>
              </header>

              {/* Year in Pixels Grid */}
              <div className="grid grid-cols-7 gap-2 mb-10">
                {/* Generate 28 dummy squares + actual logs for demo */}
                {[...Array(28)].map((_, i) => {
                  const logAtDate = logs[i]; // Simple mapping for demo
                  const color = logAtDate ? MOOD_COLORS[logAtDate.core] : 'rgba(0,0,0,0.05)';
                  
                  return (
                    <motion.div
                      key={i}
                      whileHover={{ scale: 1.1 }}
                      className="aspect-square rounded-sm shadow-sm"
                      style={{ backgroundColor: color }}
                      title={logAtDate ? `${logAtDate.core}: ${logAtDate.note}` : 'No entry'}
                    />
                  );
                })}
              </div>

              {/* Simple Insights */}
              <div className="bg-white/10 p-6 rounded-3xl backdrop-blur-md border border-white/20">
                <h3 className="text-sm uppercase tracking-widest opacity-50 mb-4">Insights</h3>
                <div className="flex justify-between items-center">
                  <span>Most frequent mood</span>
                  <span className="font-bold text-lg">Peaceful</span>
                </div>
              </div>
            </motion.div>
          )}

        </AnimatePresence>
      </main>
    </div>
  );
}

// Logic for the selector step (Simplified for display)
function MoodSelectorComponent({ onComplete }) {
  // Use the logic from the previous prompt here...
  return (
    <div className="text-center">
      {/* ... selector UI ... */}
      <button onClick={onComplete} className="mt-10 opacity-50 italic">Skip to see Patterns →</button>
    </div>
  );
}
