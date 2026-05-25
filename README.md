import { useState } from 'react';
import {
  ChevronDown, Menu, X, ArrowRight, Search, Globe,
  Atom, TrendingUp, Shield, Target, GitBranch, Lock,
  Building2, BarChart3, Activity
} from 'lucide-react';
import {
  AreaChart, Area, XAxis, YAxis, CartesianGrid, Tooltip, ResponsiveContainer
} from 'recharts';

const C = {
  bg: '#ffffff',
  surface: '#f7f5f1',
  ink: '#1a1814',
  inkSoft: '#3d3833',
  inkDim: '#6b645c',
  inkMute: '#9c948a',
  border: '#e6e1d8',
  borderLight: '#f0ebe2',
  brand: '#3d2817',
  brandSoft: '#6b4423',
  accent: '#826644',
  gold: '#a87f3d',
};

function TopBar() {
  return (
    <div className="hidden md:flex items-center justify-end gap-6 px-6 py-2 text-[11px] text-stone-600 border-b" style={{ borderColor: C.borderLight, background: C.surface }}>
      <a href="#" className="hover:text-stone-900 transition">Careers</a>
      <a href="#" className="hover:text-stone-900 transition">News</a>
      <a href="#" className="hover:text-stone-900 transition">Contact Us</a>
      <a href="#" className="hover:text-stone-900 transition">Login</a>
      <button className="flex items-center gap-1.5 hover:text-stone-900 transition">
        <Globe size={11} />
        Global
        <ChevronDown size={10} />
      </button>
    </div>
  );
}

function MainNav() {
  const [menuOpen, setMenuOpen] = useState(false);
  const nav = ['Solutions', 'Who We Serve', 'Insights', 'About Us'];
  return (
    <header className="sticky top-0 z-50 bg-white border-b" style={{ borderColor: C.border }}>
      <TopBar />
      <div className="flex items-center justify-between px-4 md:px-8 py-5">
        <div className="flex items-center gap-12">
          <a href="#" className="flex items-baseline gap-2">
            <div className="font-serif text-[22px] leading-none tracking-tight" style={{ color: C.ink }}>
              Jay <span style={{ color: C.brandSoft }}>&</span> Brandon's
            </div>
            <div className="font-serif text-[22px] leading-none tracking-tight" style={{ color: C.ink }}>
              양자역학
            </div>
          </a>
          <nav className="hidden lg:flex items-center gap-8">
            {nav.map((item) => (
              <a
                key={item}
                href="#"
                className="text-[14px] font-medium hover:text-amber-900 transition-colors py-1 border-b-2 border-transparent hover:border-amber-900"
                style={{ color: C.inkSoft }}
              >
                {item}
              </a>
            ))}
          </nav>
        </div>
        <div className="flex items-center gap-4">
          <button className="hidden md:block" style={{ color: C.inkSoft }}>
            <Search size={18} />
          </button>
          <button className="lg:hidden" onClick={() => setMenuOpen(!menuOpen)} style={{ color: C.ink }}>
            {menuOpen ? <X size={22} /> : <Menu size={22} />}
          </button>
        </div>
      </div>
      {menuOpen && (
        <div className="lg:hidden border-t px-4 py-3 space-y-2" style={{ borderColor: C.border }}>
          {nav.map((item) => (
            <a key={item} href="#" className="block py-2 text-sm" style={{ color: C.inkSoft }}>{item}</a>
          ))}
        </div>
      )}
    </header>
  );
}

function Hero() {
  return (
    <section style={{ background: C.surface }}>
      <div className="max-w-7xl mx-auto px-4 md:px-8 py-16 md:py-24">
        <div className="grid lg:grid-cols-2 gap-12 lg:gap-20 items-center">
          <div>
            <div className="text-[11px] tracking-[0.25em] uppercase mb-6" style={{ color: C.brandSoft }}>
              Edition · 2026
            </div>
            <h1 className="font-serif text-5xl md:text-6xl lg:text-7xl leading-[1.05] mb-6" style={{ color: C.ink }}>
              Jay & Brandon's
              <br />
              <span style={{ color: C.brandSoft, fontStyle: 'italic' }}>양자역학</span>
            </h1>
            <p className="text-lg leading-relaxed mb-8 max-w-lg" style={{ color: C.inkSoft }}>
              양자컴퓨팅이 금융을 어떻게 다시 쓰고 있는지 — 물리학의 원리에서 글로벌 은행들의 실제 도입 사례까지 한 곳에서 살펴봅니다.
            </p>
            <a href="#insights" className="inline-flex items-center gap-3 group" style={{ color: C.brand }}>
              <span className="text-sm font-medium border-b pb-1" style={{ borderColor: C.brand }}>
                인사이트 보기
              </span>
              <ArrowRight size={16} className="transition-transform group-hover:translate-x-1" />
            </a>
          </div>
          <div className="relative">
            <div className="aspect-[4/5] overflow-hidden relative" style={{ background: `linear-gradient(135deg, ${C.brand} 0%, ${C.brandSoft} 50%, ${C.gold} 100%)` }}>
              <svg viewBox="0 0 400 500" className="absolute inset-0 w-full h-full opacity-50">
                <defs>
                  <radialGradient id="orbGrad" cx="0.3" cy="0.3">
                    <stop offset="0%" stopColor="rgba(255,255,255,0.4)" />
                    <stop offset="100%" stopColor="rgba(255,255,255,0)" />
                  </radialGradient>
                </defs>
                <circle cx="200" cy="250" r="140" fill="url(#orbGrad)" />
                <ellipse cx="200" cy="250" rx="160" ry="40" fill="none" stroke="rgba(255,255,255,0.3)" strokeWidth="1" />
                <ellipse cx="200" cy="250" rx="160" ry="40" fill="none" stroke="rgba(255,255,255,0.2)" strokeWidth="1" transform="rotate(60 200 250)" />
                <ellipse cx="200" cy="250" rx="160" ry="40" fill="none" stroke="rgba(255,255,255,0.2)" strokeWidth="1" transform="rotate(120 200 250)" />
                <circle cx="200" cy="250" r="6" fill="white" />
              </svg>
              <div className="absolute bottom-8 left-8 right-8 text-white">
                <div className="text-[10px] tracking-[0.3em] uppercase mb-3 opacity-80">A Field Guide</div>
                <div className="font-serif text-2xl leading-tight">Quantum Computing<br />Meets Finance</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  );
}

function FeaturedGrid() {
  const featured = [
    {
      tag: 'Letter',
      title: "Jay & Brandon's Letter to Readers",
      desc: '왜 우리가 양자컴퓨팅과 금융이라는 주제에 빠져들었는지, 그리고 이 분야가 향후 10년을 어떻게 바꿀지에 대한 우리의 시각.',
      cta: 'Read more',
      gradient: `linear-gradient(135deg, #5c4530 0%, #8a6b48 100%)`,
      icon: Atom,
    },
    {
      tag: 'Insight',
      title: '글로벌 은행이 양자에 베팅하는 이유',
      desc: '15개 이상의 글로벌 은행이 이미 양자컴퓨팅 연구에 뛰어들었습니다. JPMorgan, Goldman Sachs, HSBC의 실제 사례.',
      cta: 'Learn more',
      gradient: `linear-gradient(135deg, #3d2817 0%, #6b4423 100%)`,
      icon: Building2,
    },
    {
      tag: 'Research',
      title: '양자 알고리즘이 가속하는 금융 계산',
      desc: 'Monte Carlo는 4배 적은 표본으로, 리스크 분석은 25배 빠르게. Quantum Amplitude Estimation의 힘.',
      cta: 'Read more',
      gradient: `linear-gradient(135deg, #826644 0%, #a87f3d 100%)`,
      icon: TrendingUp,
    },
  ];
  return (
    <section className="bg-white">
      <div className="max-w-7xl mx-auto px-4 md:px-8 py-16 md:py-24">
        <div className="grid md:grid-cols-3 gap-8 md:gap-6">
          {featured.map((f, i) => (
            <article key={i} className="group cursor-pointer">
              <div className="aspect-[4/3] mb-5 relative overflow-hidden" style={{ background: f.gradient }}>
                <div className="absolute inset-0 flex items-center justify-center opacity-30 group-hover:opacity-50 transition-opacity duration-500">
                  <f.icon size={80} color="white" strokeWidth={1} />
                </div>
                <div className="absolute top-4 left-4 text-[10px] tracking-[0.25em] uppercase text-white/80">
                  {f.tag}
                </div>
              </div>
              <h3 className="font-serif text-2xl leading-snug mb-3" style={{ color: C.ink }}>
                {f.title}
              </h3>
              <p className="text-[15px] leading-relaxed mb-4" style={{ color: C.inkSoft }}>
                {f.desc}
              </p>
              <span className="inline-flex items-center gap-2 text-sm font-medium border-b pb-0.5 transition-all group-hover:gap-3" style={{ color: C.brand, borderColor: C.brand }}>
                {f.cta} <ArrowRight size={14} />
              </span>
            </article>
          ))}
        </div>
      </div>
    </section>
  );
}

function Mission() {
  return (
    <section style={{ background: C.surface }}>
      <div className="max-w-5xl mx-auto px-4 md:px-8 py-20 md:py-28 text-center">
        <div className="text-[11px] tracking-[0.3em] uppercase mb-6" style={{ color: C.brandSoft }}>
          Our Mission
        </div>
        <h2 className="font-serif text-3xl md:text-5xl leading-[1.2] mb-8" style={{ color: C.ink }}>
          물리학과 금융의 교차점에서 시작된
          <br />
          가장 흥미로운 기술 혁명
        </h2>
        <p className="text-lg leading-relaxed max-w-3xl mx-auto" style={{ color: C.inkSoft }}>
          양자컴퓨팅은 단순히 빠른 컴퓨터가 아닙니다. 완전히 다른 계산 모델로, 금융이 오랫동안 풀지 못한
          최적화·시뮬레이션 문제를 새로운 방식으로 다룹니다. 이 사이트는 그 변화의 지도입니다.
        </p>
        <a href="#about" className="inline-flex items-center gap-2 mt-10 text-sm font-medium border-b pb-1" style={{ color: C.brand, borderColor: C.brand }}>
          더 자세히 알아보기 <ArrowRight size={14} />
        </a>
      </div>
    </section>
  );
}

function Solutions() {
  const solutions = [
    { icon: Target, title: '포트폴리오 최적화', desc: '수천 개 자산을 수십 가지 제약 조건 하에 최적 배분. NP-hard 문제를 QAOA로 가속.', detail: 'Deloitte: 계산 시간 50% 단축' },
    { icon: BarChart3, title: '파생상품 가격 산정', desc: 'Monte Carlo 시뮬레이션을 Quantum Amplitude Estimation으로 가속. 표본 크기 4배 절감.', detail: 'HSBC: 가격 오차 22% 감소' },
    { icon: Activity, title: '리스크 분석', desc: 'VaR, CVaR 계산. 수만 개 스트레스 시나리오를 양자 병렬로 평가.', detail: 'Goldman Sachs: 25배 가속' },
    { icon: Shield, title: '사기 탐지', desc: '양자 머신러닝(QML)으로 거래 패턴 이상 탐지. 양자 커널이 비선형 특징 추출.', detail: 'QSVC: F1 점수 0.98' },
    { icon: GitBranch, title: '양자 머신러닝', desc: '시장 미시구조 예측, 신용 평가. 양자 커널과 변분 회로(VQC)가 핵심.', detail: 'Hybrid 워크플로우' },
    { icon: Lock, title: '양자내성암호', desc: 'Shor 알고리즘이 RSA/ECC를 깰 수 있어 NIST 표준 PQC로 전환 중.', detail: 'JPMorgan: 연 수조 달러 보안' },
  ];
  return (
    <section className="bg-white">
      <div className="max-w-7xl mx-auto px-4 md:px-8 py-20 md:py-28">
        <div className="mb-14 max-w-3xl">
          <div className="text-[11px] tracking-[0.3em] uppercase mb-4" style={{ color: C.brandSoft }}>
            Solutions
          </div>
          <h2 className="font-serif text-4xl md:text-5xl leading-tight mb-5" style={{ color: C.ink }}>
            양자가 풀 수 있는 문제들
          </h2>
          <p className="text-base leading-relaxed" style={{ color: C.inkSoft }}>
            금융의 어떤 영역에서 양자컴퓨팅이 가장 빠르게 실용적 가치를 만들어낼까요? 여섯 개의 핵심 응용 분야를 정리했습니다.
          </p>
        </div>
        <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-px" style={{ background: C.border }}>
          {solutions.map((s, i) => (
            <div key={i} className="bg-white p-8 hover:bg-stone-50 transition-colors duration-300 cursor-pointer group">
              <div className="mb-6">
                <s.icon size={36} strokeWidth={1.25} style={{ color: C.brandSoft }} />
              </div>
              <h3 className="font-serif text-xl mb-3" style={{ color: C.ink }}>{s.title}</h3>
              <p className="text-sm leading-relaxed mb-5" style={{ color: C.inkSoft }}>{s.desc}</p>
              <div className="text-xs pt-4 border-t" style={{ color: C.brandSoft, borderColor: C.borderLight }}>
                {s.detail}
              </div>
              <div className="mt-4 inline-flex items-center gap-1.5 text-xs font-medium opacity-0 group-hover:opacity-100 transition-opacity" style={{ color: C.brand }}>
                Learn more <ArrowRight size={11} />
              </div>
            </div>
          ))}
        </div>
      </div>
    </section>
  );
}

function MarketData() {
  const marketSize = [
    { year: '2023', size: 0.83, invest: 8 },
    { year: '2024', size: 1.12, invest: 11 },
    { year: '2025', size: 1.67, invest: 16 },
    { year: '2026', size: 2.15, invest: 21 },
    { year: '2027', size: 2.68, invest: 26 },
    { year: '2028', size: 3.22, invest: 32 },
  ];
  return (
    <section style={{ background: C.surface }} id="insights">
      <div className="max-w-7xl mx-auto px-4 md:px-8 py-20 md:py-28">
        <div className="grid lg:grid-cols-12 gap-12 items-end mb-14">
          <div className="lg:col-span-7">
            <div className="text-[11px] tracking-[0.3em] uppercase mb-4" style={{ color: C.brandSoft }}>
              Market Intelligence
            </div>
            <h2 className="font-serif text-4xl md:text-5xl leading-tight" style={{ color: C.ink }}>
              자본은 이미 움직이고 있다
            </h2>
          </div>
          <div className="lg:col-span-5">
            <p className="text-base leading-relaxed" style={{ color: C.inkSoft }}>
              2025년 글로벌 양자 컴퓨팅 투자는 <strong style={{ color: C.ink }}>$16B</strong> — 2년 만에 두 배 성장.
              금융은 응용 분야의 약 20%를 차지하며 가장 빠르게 성장하는 영역입니다.
            </p>
          </div>
        </div>

        <div className="grid lg:grid-cols-4 gap-px mb-12" style={{ background: C.border }}>
          {[
            { label: '시장 규모', value: '$1.67B', sub: '2025 글로벌' },
            { label: '총 투자', value: '$16B', sub: '전년 대비 +100%' },
            { label: '금융 비중', value: '~20%', sub: '전체 응용 중' },
            { label: '2035 잠재 가치', value: '$400-600B', sub: 'McKinsey 추정' },
          ].map((s) => (
            <div key={s.label} className="bg-white p-8">
              <div className="text-[10px] tracking-[0.25em] uppercase mb-3" style={{ color: C.inkMute }}>{s.label}</div>
              <div className="font-serif text-3xl mb-1" style={{ color: C.ink }}>{s.value}</div>
              <div className="text-xs" style={{ color: C.inkDim }}>{s.sub}</div>
            </div>
          ))}
        </div>

        <div className="bg-white p-8 md:p-10 border" style={{ borderColor: C.border }}>
          <div className="flex items-baseline justify-between mb-2">
            <h3 className="font-serif text-2xl" style={{ color: C.ink }}>시장 규모 & 투자 추이</h3>
            <div className="text-[10px] tracking-[0.25em] uppercase" style={{ color: C.inkMute }}>USD Billion</div>
          </div>
          <p className="text-sm mb-8" style={{ color: C.inkDim }}>2026 이후는 추정치 · 출처: CoinLaw, McKinsey 종합</p>
          <ResponsiveContainer width="100%" height={320}>
            <AreaChart data={marketSize}>
              <defs>
                <linearGradient id="g1" x1="0" y1="0" x2="0" y2="1">
                  <stop offset="0%" stopColor={C.brandSoft} stopOpacity={0.35} />
                  <stop offset="100%" stopColor={C.brandSoft} stopOpacity={0} />
                </linearGradient>
                <linearGradient id="g2" x1="0" y1="0" x2="0" y2="1">
                  <stop offset="0%" stopColor={C.gold} stopOpacity={0.3} />
                  <stop offset="100%" stopColor={C.gold} stopOpacity={0} />
                </linearGradient>
              </defs>
              <CartesianGrid stroke={C.borderLight} strokeDasharray="0" vertical={false} />
              <XAxis dataKey="year" stroke={C.inkDim} tick={{ fontSize: 12 }} axisLine={{ stroke: C.border }} tickLine={false} />
              <YAxis stroke={C.inkDim} tick={{ fontSize: 11 }} axisLine={false} tickLine={false} />
              <Tooltip
                contentStyle={{ background: 'white', border: `1px solid ${C.border}`, borderRadius: 4, fontSize: 12 }}
                labelStyle={{ color: C.ink, fontWeight: 600 }}
              />
              <Area type="monotone" dataKey="invest" stroke={C.gold} strokeWidth={2} fill="url(#g2)" name="투자 ($B)" />
              <Area type="monotone" dataKey="size" stroke={C.brandSoft} strokeWidth={2.5} fill="url(#g1)" name="시장 규모 ($B)" />
            </AreaChart>
          </ResponsiveContainer>
        </div>
      </div>
    </section>
  );
}

function Banks() {
  const banks = [
    { name: 'JPMorgan Chase', country: 'United States', focus: '양자 알고리즘 연구', highlight: '연간 수조 달러 거래 보안' },
    { name: 'Goldman Sachs', country: 'United States', focus: '리스크 분석', highlight: '리스크 분석 25배 향상' },
    { name: 'HSBC', country: 'United Kingdom', focus: '파생상품 가격', highlight: '가격 오차 22% 감소' },
    { name: 'Deutsche Bank', country: 'Germany', focus: '양자 리스크 도구', highlight: '$400M 투자' },
    { name: 'BBVA', country: 'Spain', focus: '포트폴리오 최적화', highlight: 'Monte Carlo 가속' },
    { name: 'BNP Paribas', country: 'France', focus: '파생상품·QML', highlight: '중성원자 시스템 연구' },
  ];
  return (
    <section className="bg-white">
      <div className="max-w-7xl mx-auto px-4 md:px-8 py-20 md:py-28">
        <div className="grid lg:grid-cols-12 gap-12 mb-14 items-end">
          <div className="lg:col-span-7">
            <div className="text-[11px] tracking-[0.3em] uppercase mb-4" style={{ color: C.brandSoft }}>
              Industry Leaders
            </div>
            <h2 className="font-serif text-4xl md:text-5xl leading-tight" style={{ color: C.ink }}>
              누가 양자에 뛰어들고 있나
            </h2>
          </div>
          <div className="lg:col-span-5">
            <p className="text-base leading-relaxed" style={{ color: C.inkSoft }}>
              아직 라이브 거래에 양자 컴퓨터를 쓰는 은행은 없지만, 15개 이상의 글로벌 은행이 PoC 단계를 지나
              양자 우위 실증과 PQC 전환을 동시에 추진하고 있습니다.
            </p>
          </div>
        </div>
        <div className="border-t" style={{ borderColor: C.border }}>
          {banks.map((b, i) => (
            <div
              key={i}
              className="grid grid-cols-12 gap-4 md:gap-8 py-7 border-b items-baseline hover:bg-stone-50 transition-colors cursor-pointer group"
              style={{ borderColor: C.border }}
            >
              <div className="col-span-1 font-mono text-xs" style={{ color: C.inkMute }}>
                {String(i + 1).padStart(2, '0')}
              </div>
              <div className="col-span-11 md:col-span-4">
                <div className="font-serif text-xl md:text-2xl" style={{ color: C.ink }}>{b.name}</div>
                <div className="text-xs mt-1" style={{ color: C.inkMute }}>{b.country}</div>
              </div>
              <div className="col-span-6 md:col-span-3 text-sm" style={{ color: C.inkSoft }}>
                {b.focus}
              </div>
              <div className="col-span-5 md:col-span-3 text-sm md:text-right" style={{ color: C.brandSoft }}>
                {b.highlight}
              </div>
              <div className="hidden md:flex col-span-1 justify-end opacity-0 group-hover:opacity-100 transition-opacity" style={{ color: C.brand }}>
                <ArrowRight size={16} />
              </div>
            </div>
          ))}
        </div>
      </div>
    </section>
  );
}

function Timeline() {
  const timeline = [
    { year: '2026', title: '양자 우위 달성', desc: 'IBM은 특정 문제에서 양자 컴퓨터가 고전 컴퓨터를 능가하는 시점을 2026년 말로 전망. 금융 분야 첫 실용 사례 등장.' },
    { year: '2027-28', title: 'NISQ 최적화 시대', desc: '하이브리드(고전+양자) 워크플로우가 표준. QAOA 기반 포트폴리오 최적화가 일부 펀드 운용에 사용 시작.' },
    { year: '2029', title: 'IBM 대규모 FTQC', desc: '수백 개 논리 큐비트, 1억 회 연산 가능한 결함 허용 양자 컴퓨터. 금융 최적화 가속.' },
    { year: '2030+', title: 'PQC 전면 전환', desc: 'NIST 표준 양자내성암호로 글로벌 금융 시스템 마이그레이션 완료.' },
    { year: '2035', title: '본격 양자 금융', desc: 'McKinsey 추정 금융 분야 양자 가치 $400B-$600B 실현. 양자 ML 기반 헤지펀드 등장.' },
  ];
  return (
    <section style={{ background: C.surface }}>
      <div className="max-w-6xl mx-auto px-4 md:px-8 py-20 md:py-28">
        <div className="mb-14">
          <div className="text-[11px] tracking-[0.3em] uppercase mb-4" style={{ color: C.brandSoft }}>
            Roadmap
          </div>
          <h2 className="font-serif text-4xl md:text-5xl leading-tight max-w-3xl" style={{ color: C.ink }}>
            언제, 어떻게 현실이 될까
          </h2>
        </div>
        <div className="space-y-px" style={{ background: C.border }}>
          {timeline.map((t, i) => (
            <div key={i} className="bg-white p-8 md:p-10 grid md:grid-cols-12 gap-6 md:gap-10 items-baseline">
              <div className="md:col-span-2">
                <div className="font-serif text-3xl" style={{ color: C.brandSoft }}>{t.year}</div>
              </div>
              <div className="md:col-span-3">
                <h4 className="font-serif text-xl" style={{ color: C.ink }}>{t.title}</h4>
              </div>
              <div className="md:col-span-7 text-[15px] leading-relaxed" style={{ color: C.inkSoft }}>
                {t.desc}
              </div>
            </div>
          ))}
        </div>
      </div>
    </section>
  );
}

function Footer() {
  return (
    <footer className="bg-white border-t" style={{ borderColor: C.border }}>
      <div className="max-w-7xl mx-auto px-4 md:px-8 py-16">
        <div className="grid md:grid-cols-4 gap-10 mb-12">
          <div>
            <div className="font-serif text-sm tracking-[0.2em] uppercase mb-5" style={{ color: C.inkMute }}>
              Solutions
            </div>
            <ul className="space-y-3 text-sm" style={{ color: C.inkSoft }}>
              <li><a href="#" className="hover:text-amber-900">포트폴리오 최적화</a></li>
              <li><a href="#" className="hover:text-amber-900">파생상품 가격</a></li>
              <li><a href="#" className="hover:text-amber-900">리스크 분석</a></li>
              <li><a href="#" className="hover:text-amber-900">사기 탐지</a></li>
              <li><a href="#" className="hover:text-amber-900">양자 머신러닝</a></li>
              <li><a href="#" className="hover:text-amber-900">양자내성암호</a></li>
            </ul>
          </div>
          <div>
            <div className="font-serif text-sm tracking-[0.2em] uppercase mb-5" style={{ color: C.inkMute }}>
              Insights
            </div>
            <ul className="space-y-3 text-sm" style={{ color: C.inkSoft }}>
              <li><a href="#" className="hover:text-amber-900">양자역학 기초</a></li>
              <li><a href="#" className="hover:text-amber-900">양자컴퓨터 원리</a></li>
              <li><a href="#" className="hover:text-amber-900">시장 현황</a></li>
              <li><a href="#" className="hover:text-amber-900">미래 전망</a></li>
            </ul>
          </div>
          <div>
            <div className="font-serif text-sm tracking-[0.2em] uppercase mb-5" style={{ color: C.inkMute }}>
              About
            </div>
            <ul className="space-y-3 text-sm" style={{ color: C.inkSoft }}>
              <li><a href="#" className="hover:text-amber-900">소개</a></li>
              <li><a href="#" className="hover:text-amber-900">출처 & 참고문헌</a></li>
              <li><a href="#" className="hover:text-amber-900">문의</a></li>
            </ul>
          </div>
          <div>
            <div className="font-serif text-sm tracking-[0.2em] uppercase mb-5" style={{ color: C.inkMute }}>
              Connect
            </div>
            <ul className="space-y-3 text-sm" style={{ color: C.inkSoft }}>
              <li>Jay & Brandon</li>
              <li>2026 Edition</li>
            </ul>
          </div>
        </div>
        <div className="pt-8 border-t flex flex-col md:flex-row md:items-center justify-between gap-4" style={{ borderColor: C.border }}>
          <div className="flex items-baseline gap-3">
            <div className="font-serif text-xl" style={{ color: C.ink }}>
              Jay <span style={{ color: C.brandSoft }}>&</span> Brandon's <span style={{ color: C.brand }}>양자역학</span>
            </div>
          </div>
          <div className="text-xs" style={{ color: C.inkMute }}>
            © 2026 Jay & Brandon. 교육·정보 제공 목적. 투자 자문이 아닙니다.
          </div>
        </div>
        <div className="mt-6 text-[11px] leading-relaxed" style={{ color: C.inkMute }}>
          출처: McKinsey · IBM Quantum · The Quantum Insider · CoinLaw · arXiv · QuantumZeitgeist · Springer Computational Economics ·
          데이터는 2025년 기준이며 2026년 5월 업데이트.
        </div>
      </div>
    </footer>
  );
}

export default function App() {
  return (
    <div className="min-h-screen" style={{ background: C.bg, color: C.ink }}>
      <style>{`
        @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,600;1,400;1,500&family=Inter:wght@400;500;600&display=swap');
        body { font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif; -webkit-font-smoothing: antialiased; }
        .font-serif { font-family: 'Playfair Display', Georgia, serif; }
        .font-mono { font-family: ui-monospace, 'SF Mono', Menlo, monospace; }
      `}</style>
      <MainNav />
      <Hero />
      <FeaturedGrid />
      <Mission />
      <Solutions />
      <MarketData />
      <Banks />
      <Timeline />
      <Footer />
    </div>
  );
}
