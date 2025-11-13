# 1. Cria app com Vite + React + TS
npm create vite@latest criptomente-app -- --template react-ts
cd criptomente-app

# 2. Instala dependências essenciais
npm install
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
npm install react-router-dom axios react-icons localforage

# 3. Configura Tailwind (substitua o conteúdo de tailwind.config.cjs)
cat > tailwind.config.cjs <<'TWC' 
module.exports = {
  content: ["./index.html","./src/**/*.{ts,tsx,js,jsx}"],
  theme: { extend: {} },
  plugins: [],
}
TWC

# 4. Cria arquivos iniciais de conteúdo / estrutura (componentes e conteúdo)
mkdir -p src/data src/pages src/components src/styles
cat > src/data/content.json <<'JSON'
{
  "brand": {"name":"CriptoMente","tag":"Mentoria & Educação Cripto","contact":"@criptomente"},
  "modules":[
    {"id":"intro","title":"Mentalidade Cripto","content":"Ganhar com criptomoedas começa com mentalidade: aprender, disciplina e gestão de risco."},
    {"id":"o-que-sao","title":"O que são criptomoedas","content":"Explicação simples sobre blockchain, Bitcoin, Ethereum e stablecoins."},
    {"id":"como-ganhar","title":"Como ganhar dinheiro","content":"Holding, Trading e Renda Passiva (staking/DeFi); quando usar cada uma."},
    {"id":"seguranca","title":"Segurança","content":"2FA, cold wallets, backups de seed e higiene digital."},
    {"id":"estrategias","title":"Estratégias Avançadas","content":"DCA, diversificação, análise de fundamentos e gestão de risco."}
  ],
  "quotes":[
    {"author":"Andreas Antonopoulos","text":"Se não é sua chave, não é seu dinheiro."},
    {"author":"Vitalik Buterin","text":"Não se trata apenas de investir, mas de construir novas infraestruturas."},
    {"author":"Elon Musk","text":"Bitcoin é uma revolução tecnológica e financeira."},
    {"author":"CZ (Binance)","text":"Descentralização é uma das maiores inovações da internet."},
    {"author":"Warren Buffett","text":"O tempo no mercado é mais importante que o timing do mercado."}
  ]
}
JSON

# 5. Cria App e páginas básicas (Home, Module, Checklist)
cat > src/main.tsx <<'TSX'
import React from "react";
import ReactDOM from "react-dom/client";
import { BrowserRouter, Routes, Route } from "react-router-dom";
import "./styles/index.css";
import Home from "./pages/Home";
import Module from "./pages/Module";
import Checklist from "./pages/Checklist";

ReactDOM.createRoot(document.getElementById("root")!).render(
  <React.StrictMode>
    <BrowserRouter>
      <Routes>
        <Route path='/' element={<Home/>}/>
        <Route path='/module/:id' element={<Module/>}/>
        <Route path='/checklist' element={<Checklist/>}/>
      </Routes>
    </BrowserRouter>
  </React.StrictMode>
);
TSX

cat > src/pages/Home.tsx <<'TSX'
import React from 'react';
import data from '../data/content.json';
import { Link } from 'react-router-dom';

export default function Home(){
  return (
    <div className='min-h-screen bg-black text-gray-200 p-8'>
      <header className='max-w-4xl mx-auto text-center'>
        <h1 className='text-4xl text-yellow-400 font-bold'>{data.brand.name}</h1>
        <p className='mt-2 text-gray-300'>{data.brand.tag}</p>
      </header>

      <main className='max-w-4xl mx-auto mt-8'>
        <section className='bg-gray-900 p-6 rounded-lg shadow-lg'>
          <h2 className='text-2xl text-yellow-400 mb-2'>Aprenda a ganhar com cripto</h2>
          <p className='text-gray-300'>Conteúdo prático para iniciantes e veteranos: mentalidade, segurança e estratégias reais.</p>
        </section>

        <section className='grid gap-4 mt-6'>
          {data.modules.map((m)=>(
            <Link key={m.id} to={'/module/'+m.id} className='block p-4 bg-gray-900 rounded-lg hover:bg-gray-800'>
              <h3 className='text-xl text-yellow-400'>{m.title}</h3>
              <p className='text-gray-300 mt-1'>{m.content.substring(0,120)}...</p>
            </Link>
          ))}
        </section>

        <section className='mt-6 text-center'>
          <Link to='/checklist' className='inline-block bg-yellow-400 text-black px-6 py-3 rounded-full font-bold'>Abrir Checklist</Link>
        </section>

        <section className='mt-8'>
          <h3 className='text-yellow-400'>Citações</h3>
          <ul className='mt-3 space-y-2'>
            {data.quotes.map((q,idx)=>(
              <li key={idx} className='text-gray-300 italic'>&ldquo;{q.text}&rdquo; — <strong className='text-yellow-300'>{q.author}</strong></li>
            ))}
          </ul>
        </section>
      </main>
    </div>
  )
}
TSX

cat > src/pages/Module.tsx <<'TSX'
import React from 'react';
import { useParams, Link } from 'react-router-dom';
import data from '../data/content.json';

export default function Module(){
  const { id } = useParams();
  const module = data.modules.find(m=>m.id===id);
  if(!module) return <div className='p-8'>Módulo não encontrado. <Link to='/'>Voltar</Link></div>;
  return (
    <div className='min-h-screen bg-black p-8 text-gray-200'>
      <div className='max-w-3xl mx-auto'>
        <Link to='/' className='text-yellow-400'>&larr; Voltar</Link>
        <h1 className='text-3xl text-yellow-400 mt-4'>{module.title}</h1>
        <p className='mt-4 text-gray-300'>{module.content}</p>

        {/* Aqui você adiciona passos detalhados; exemplo para 'como-ganhar' */}
        {module.id==='como-ganhar' && (
          <div className='mt-6'>
            <h2 className='text-yellow-300'>Passo a passo prático</h2>
            <ol className='list-decimal ml-6 mt-2 text-gray-300'>
              <li>Aprenda o básico: blockchain, chaves, exchanges.</li>
              <li>Abra conta em uma exchange confiável e habilite 2FA.</li>
              <li>Comece com DCA: invista pequeno valor mensal.</li>
              <li>Estude fundamentos antes de comprar altcoins.</li>
              <li>Use uma wallet cold para reserva de valor.</li>
            </ol>
          </div>
        )}
      </div>
    </div>
  )
}
TSX

cat > src/pages/Checklist.tsx <<'TSX'
import React, {useState} from 'react';

const items = [
  'Configurar 2FA na exchange',
  'Fazer backup da seed da wallet',
  'Iniciar DCA (valor mensal)',
  'Revisar taxas e segurança'
];

export default function Checklist(){
  const [checked, setChecked] = useState<boolean[]>(new Array(items.length).fill(false));
  return (
    <div className='min-h-screen bg-black p-8 text-gray-200'>
      <div className='max-w-3xl mx-auto bg-gray-900 p-6 rounded-lg'>
        <h1 className='text-2xl text-yellow-400'>Checklist CriptoMente</h1>
        <ul className='mt-4 space-y-3'>
          {items.map((it,i)=>(
            <li key={i} className='flex items-center gap-3'>
              <input type='checkbox' checked={checked[i]} onChange={()=>{const c=[...checked]; c[i]=!c[i]; setChecked(c);} }/>
              <span className='text-gray-300'>{it}</span>
            </li>
          ))}
        </ul>
        <div className='mt-4'>
          <button className='bg-yellow-400 text-black px-4 py-2 rounded' onClick={()=>alert('Checklist salvo localmente (exemplo)')}>Salvar</button>
        </div>
      </div>
    </div>
  )
}
TSX

# 6. Cria estilos base (Tailwind entrada)
cat > src/styles/index.css <<'CSS'
@tailwind base;
@tailwind components;
@tailwind utilities;
body { @apply bg-black; }
CSS

# 7. Adiciona scripts e inicia dev server
npm run dev
