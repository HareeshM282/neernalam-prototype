<!doctype html><html><head><meta charset=utf8><meta name=viewport content="width=device-width,initial-scale=1,viewport-fit=cover"><style>:root{color-scheme:light;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}html{scroll-padding-top:env(safe-area-inset-top,0px)}body{margin:0;padding:0;font:14px -apple-system,BlinkMacSystemFont,sans-serif;background:#fff;color:#000}img{max-width:100%}[hidden]:not([hidden=until-found i]){display:none!important}</style></head><body>
<title>NEER NALAM</title>
<meta name="claude:viewport-fit-sides" content="cover">
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Source+Serif+4:opsz,wght@8..60,500;8..60,600;8..60,700&display=swap">
<script src="https://cdn.tailwindcss.com/3.4.17"></script>
<script>
tailwind.config = { theme: { extend: {
  fontFamily: { sans: ['Inter','system-ui','sans-serif'], serif: ['Source Serif 4','Georgia','serif'] },
  colors: {
    navy: { 950:'#071428', 900:'#0A1B33', 800:'#0F2747', 700:'#17355F', 600:'#234677', 100:'#E3EAF3', 50:'#F1F5F9' },
    teal: { 50:'#EFF8F8', 100:'#DCEFEF', 200:'#BDE0E0', 300:'#96CDCD', 400:'#6FB9BA', 500:'#4AA0A3', 600:'#37878A', 700:'#2B6D70' }
  },
  boxShadow: { soft: '0 1px 2px rgba(10,27,51,.04), 0 8px 24px -8px rgba(10,27,51,.10)', lift: '0 2px 4px rgba(10,27,51,.05), 0 18px 40px -12px rgba(10,27,51,.18)' }
} } };
</script>
<style>
:root { color-scheme: light; --page:#F4F7FA; --ink:#0A1B33; }
html, body { background: var(--page); color: var(--ink); font-family: 'Inter', system-ui, sans-serif; font-size: 15px; }
body { margin: 0; }
.gutter { padding-left: max(16px, env(safe-area-inset-left, 0px)); padding-right: max(16px, env(safe-area-inset-right, 0px)); }
h1, h2, h3, .font-serif { text-wrap: balance; }
.fade-up { animation: fadeUp .45s ease both; }
@keyframes fadeUp { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: none; } }
.hero-bg { background: radial-gradient(900px 400px at 85% -10%, rgba(111,185,186,.28), transparent 60%), linear-gradient(180deg, #0A1B33, #0F2747); }
.ring-focus:focus-visible, button:focus-visible, a:focus-visible, input:focus-visible, select:focus-visible, textarea:focus-visible { outline: 2px solid #4AA0A3; outline-offset: 2px; }
.tbl-wrap { overflow-x: auto; }
@media (prefers-reduced-motion: reduce) { .fade-up { animation: none; } * { transition: none !important; } }
</style>
<div id="root"></div>
<script src="https://cdnjs.cloudflare.com/ajax/libs/react/18.3.1/umd/react.production.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/react-dom/18.3.1/umd/react-dom.production.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/htm@3.1.1/dist/htm.js"></script>
<script>
const { useState, useEffect, useMemo, useRef, useCallback, createContext, useContext } = React;
const html = htm.bind(React.createElement);
const DAY = 864e5, HOUR = 36e5;

/* ================= SIMULATED BACKEND (DEMO MODE) =================
   All data lives in memory in this browser tab and is lost on reload.
   Every call below re-verifies the caller's role from the session token,
   the same way a real server would. The UI never decides permissions. */
const CATS = ['Drinking Water Problem','Dirty Toilet','Hand-Wash Facility Problem','Other Hygiene Issues'];
const STATUSES = ['NEW','REVIEWED','IN PROGRESS','RESOLVED'];
const TEAMS = [
  { id:'T1', name:'Plumbing & Water Works', lead:'R. Selvam', phone:'Ext. 214' },
  { id:'T2', name:'Housekeeping & Sanitation', lead:'M. Fathima', phone:'Ext. 188' },
  { id:'T3', name:'Electrical & Appliances', lead:'K. Arun', phone:'Ext. 231' }
];
const DELAY_DAYS = 3;

const photo = (kind, label) => {
  const c = { water:['#BDE0E0','#37878A'], toilet:['#DCE5F0','#234677'], wash:['#D5ECEA','#2B6D70'], other:['#E6ECF2','#17355F'] }[kind];
  const svg = `<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 480 320"><defs><linearGradient id="g" x1="0" y1="0" x2="1" y2="1"><stop offset="0" stop-color="${c[0]}"/><stop offset="1" stop-color="#F4F7FA"/></linearGradient></defs><rect width="480" height="320" fill="url(#g)"/><rect x="150" y="70" width="180" height="170" rx="18" fill="${c[1]}" opacity=".9"/><rect x="175" y="95" width="130" height="60" rx="10" fill="#fff" opacity=".85"/><circle cx="240" cy="205" r="14" fill="#fff" opacity=".85"/><text x="240" y="285" text-anchor="middle" font-family="Arial" font-size="16" fill="#0A1B33" opacity=".7">${label}</text></svg>`;
  return 'data:image/svg+xml;utf8,' + encodeURIComponent(svg);
};

const hash = async (s) => {
  try {
    const b = await crypto.subtle.digest('SHA-256', new TextEncoder().encode('nn-salt:' + s));
    return [...new Uint8Array(b)].map(x => x.toString(16).padStart(2, '0')).join('');
  } catch (e) { let h = 5381; for (const ch of 'nn-salt:' + s) h = ((h << 5) + h + ch.charCodeAt(0)) | 0; return 'weak' + h; }
};

const DB = { users: [], complaints: [], history: [], seq: 1010, hseq: 1 };
const subs = new Set();
const notify = () => subs.forEach(f => f());
const sessions = new Map();
const mkErr = (code, message) => Object.assign(new Error(message), { code });
const lag = (v) => new Promise(r => setTimeout(() => r(v), 220));

async function seed() {
  const stu = [
    ['U-S01','Ananya Krishnan','21CS1042','ananya.k@college.edu'],
    ['U-S02','Rohan Mehta','21EC2017','rohan.m@college.edu'],
    ['U-S03','Divya Raman','22ME3008','divya.r@college.edu']
  ];
  for (const [id,name,regNo,email] of stu) DB.users.push({ id, name, regNo, email, role:'STUDENT', passHash: await hash('Student@123') });
  DB.users.push({ id:'U-A01', name:'Dr. Meera Iyer', username:'admin.hygiene', email:'meera.iyer@college.edu', role:'ADMIN', passHash: await hash('Admin@123') });
  DB.users.push({ id:'U-A02', name:'Suresh Nair', username:'admin.facilities', email:'suresh.n@college.edu', role:'ADMIN', passHash: await hash('Admin@123') });
  const now = Date.now();
  const mk = (n, sid, cat, desc, b, f, r, ago, status, team, pk, pl, notes) => ({
    id:'NN-26-'+n, studentId:sid, category:cat, description:desc, building:b, floor:f, room:r,
    problemDate: new Date(now - ago*DAY).toISOString().slice(0,10), submittedAt: now - ago*DAY, status, team, photo: photo(pk, pl), internalNotes: notes || []
  });
  const H = (cid, prev, next, by, ago) => DB.history.push({ id:'H-'+(DB.hseq++), complaintId:cid, kind:'status', prev, next, by, at: now - ago*DAY });
  const C = DB.complaints;
  C.push(mk(1001,'U-S01','Drinking Water Problem','The water dispenser near the library entrance has not been dispensing water since Monday. Students are forced to walk to the next block.','Central Library','Ground Floor','Water dispenser, main entrance',6,'RESOLVED','T1','water','Water dispenser',[{by:'Dr. Meera Iyer',at:now-5*DAY,text:'Pump motor replaced by plumbing team.'}]));
  H('NN-26-1001',null,'NEW','System',6); H('NN-26-1001','NEW','REVIEWED','Dr. Meera Iyer',5.8); H('NN-26-1001','REVIEWED','IN PROGRESS','Dr. Meera Iyer',5.5); H('NN-26-1001','IN PROGRESS','RESOLVED','Dr. Meera Iyer',4.6);
  C.push(mk(1002,'U-S01','Dirty Toilet','Toilet cleaning required. The floor is wet, the dustbin is overflowing and there is a strong odour.','Block B (Mechanical)','First Floor','Gents washroom near Lab 3',2,'IN PROGRESS','T2','toilet','Washroom',[]));
  H('NN-26-1002',null,'NEW','System',2); H('NN-26-1002','NEW','REVIEWED','Suresh Nair',1.6); H('NN-26-1002','REVIEWED','IN PROGRESS','Suresh Nair',1.2);
  C.push(mk(1003,'U-S02','Hand-Wash Facility Problem','The hand-wash station outside the canteen has no water and no soap. It has been like this for a week.','Main Canteen','Ground Floor','Hand-wash station, east side',5,'NEW',null,'wash','Hand-wash station',[]));
  H('NN-26-1003',null,'NEW','System',5);
  C.push(mk(1004,'U-S03','Drinking Water Problem','The drinking water from the RO unit smells of chlorine and looks cloudy. Several students reported stomach discomfort.','Block C (Civil)','Second Floor','RO unit, corridor',0.3,'NEW',null,'water','RO water unit',[]));
  H('NN-26-1004',null,'NEW','System',0.3);
  C.push(mk(1005,'U-S02','Dirty Toilet','Ladies washroom flush is not working and the tap is leaking.','Block A (CSE)','Third Floor','Washroom near Seminar Hall',4,'REVIEWED','T1','toilet','Washroom',[{by:'Suresh Nair',at:now-3.5*DAY,text:'Waiting for spare flush valve from stores.'}]));
  H('NN-26-1005',null,'NEW','System',4); H('NN-26-1005','NEW','REVIEWED','Suresh Nair',3.5);
  C.push(mk(1006,'U-S03','Hand-Wash Facility Problem','Wash basin tap broken, water spraying on the floor.','Hostel Block 2','Ground Floor','Common wash area',1,'RESOLVED','T1','wash','Wash basin',[]));
  H('NN-26-1006',null,'NEW','System',1); H('NN-26-1006','NEW','IN PROGRESS','Dr. Meera Iyer',0.8); H('NN-26-1006','IN PROGRESS','RESOLVED','Dr. Meera Iyer',0.4);
  C.push(mk(1007,'U-S01','Other Hygiene Issues','Dustbins near the seminar hall are not being cleared. Waste is attracting flies.','Seminar Hall Complex','Ground Floor','Corridor dustbins',1.5,'NEW',null,'other','Dustbins',[]));
  H('NN-26-1007',null,'NEW','System',1.5);
}

const strip = (c) => { const { internalNotes, ...rest } = c; return rest; };
const studentView = (c) => ({ ...strip(c), history: DB.history.filter(h => h.complaintId === c.id && h.kind === 'status').map(h => ({ ...h, by: h.by === 'System' ? 'System' : 'Admin team' })) });

const api = {
  me(token) { const uid = sessions.get(token); const u = DB.users.find(x => x.id === uid); if (!u) throw mkErr(401, 'Please sign in to continue.'); return u; },
  guard(token, role) { const u = api.me(token); if (u.role !== role) throw mkErr(403, 'Access denied. Your account does not have permission for this action.'); return u; },
  async login(role, id, pw) {
    const u = DB.users.find(x => x.role === role && (role === 'STUDENT' ? x.regNo.toLowerCase() === id.trim().toLowerCase() : x.username.toLowerCase() === id.trim().toLowerCase()));
    if (!u || u.passHash !== await hash(pw)) { await lag(); throw mkErr(401, role === 'STUDENT' ? 'Register number or password is incorrect.' : 'Admin username or password is incorrect.'); }
    const token = 't' + Math.random().toString(36).slice(2) + Date.now().toString(36);
    sessions.set(token, u.id);
    const { passHash, ...safe } = u; return lag({ token, user: safe });
  },
  logout(token) { sessions.delete(token); },
  /* ---- student endpoints: always filtered to the caller's own records ---- */
  studentList(token) { const u = api.guard(token, 'STUDENT'); return DB.complaints.filter(c => c.studentId === u.id).map(studentView).sort((a, b) => b.submittedAt - a.submittedAt); },
  studentGet(token, id) { const u = api.guard(token, 'STUDENT'); const c = DB.complaints.find(x => x.id === id && x.studentId === u.id); if (!c) throw mkErr(404, 'Complaint not found.'); return studentView(c); },
  async studentCreate(token, p) {
    const u = api.guard(token, 'STUDENT');
    if (!CATS.includes(p.category)) throw mkErr(400, 'Choose a valid category.');
    if (!p.building || !p.floor || !p.room || !p.description || !p.problemDate) throw mkErr(400, 'Please complete all required fields.');
    const id = 'NN-26-' + (++DB.seq);
    const c = { id, studentId: u.id, category: p.category, description: p.description.trim(), building: p.building.trim(), floor: p.floor, room: p.room.trim(), problemDate: p.problemDate, submittedAt: Date.now(), status: 'NEW', team: null, photo: p.photo || null, internalNotes: [] };
    DB.complaints.push(c);
    DB.history.push({ id: 'H-' + (DB.hseq++), complaintId: id, kind: 'status', prev: null, next: 'NEW', by: 'System', at: Date.now() });
    notify(); broadcast(); return lag(studentView(c));
  },
  /* ---- admin endpoints: every one re-checks role === ADMIN ---- */
  adminStats(token) { api.guard(token, 'ADMIN'); const C = DB.complaints; const n = s => C.filter(c => c.status === s).length;
    return { total: C.length, new: n('NEW'), progress: n('IN PROGRESS'), resolved: n('RESOLVED'), reviewed: n('REVIEWED'), pending: C.filter(c => c.status !== 'RESOLVED').length, delayed: C.filter(api.isDelayed).length }; },
  isDelayed(c) { return c.status !== 'RESOLVED' && Date.now() - c.submittedAt > DELAY_DAYS * DAY; },
  adminList(token) { api.guard(token, 'ADMIN'); return DB.complaints.map(c => { const s = DB.users.find(u => u.id === c.studentId); return { ...c, studentName: s.name, regNo: s.regNo }; }).sort((a, b) => b.submittedAt - a.submittedAt); },
  adminGet(token, id) { api.guard(token, 'ADMIN'); const c = DB.complaints.find(x => x.id === id); if (!c) throw mkErr(404, 'Complaint not found.'); const s = DB.users.find(u => u.id === c.studentId);
    return { ...c, student: { name: s.name, regNo: s.regNo, email: s.email }, history: DB.history.filter(h => h.complaintId === id) }; },
  async adminUpdate(token, id, patch) {
    const a = api.guard(token, 'ADMIN'); const c = DB.complaints.find(x => x.id === id); if (!c) throw mkErr(404, 'Complaint not found.');
    const at = Date.now();
    if (patch.status && patch.status !== c.status) {
      if (!STATUSES.includes(patch.status)) throw mkErr(400, 'Invalid status.');
      DB.history.push({ id: 'H-' + (DB.hseq++), complaintId: id, kind: 'status', prev: c.status, next: patch.status, by: a.name, at }); c.status = patch.status;
    }
    if (patch.team !== undefined && (patch.team || null) !== c.team) {
      if (patch.team && !TEAMS.find(t => t.id === patch.team)) throw mkErr(400, 'Unknown team.');
      DB.history.push({ id: 'H-' + (DB.hseq++), complaintId: id, kind: 'assign', prev: c.team, next: patch.team || null, by: a.name, at }); c.team = patch.team || null;
    }
    if (patch.note && patch.note.trim()) { c.internalNotes.push({ by: a.name, at, text: patch.note.trim() }); DB.history.push({ id: 'H-' + (DB.hseq++), complaintId: id, kind: 'note', by: a.name, at }); }
    notify(); broadcast(); return lag(api.adminGet(token, id));
  }
};

/* Optional: two tabs of this prototype can sync complaints so the portals can be seen updating live. */
let bc = null;
try { bc = new BroadcastChannel('neer-nalam-demo'); } catch (e) {}
const broadcast = () => { try { bc && bc.postMessage({ t: 'state', complaints: DB.complaints, history: DB.history, seq: DB.seq, hseq: DB.hseq }); } catch (e) {} };
if (bc) bc.onmessage = (ev) => {
  const m = ev.data; if (!m) return;
  if (m.t === 'hello') broadcast();
  if (m.t === 'state') { DB.complaints = m.complaints; DB.history = m.history; DB.seq = Math.max(DB.seq, m.seq); DB.hseq = Math.max(DB.hseq, m.hseq); notify(); }
};
const useDB = () => { const [, f] = useState(0); useEffect(() => { const fn = () => f(x => x + 1); subs.add(fn); return () => subs.delete(fn); }, []); };

/* ================= SHARED UI ================= */
const MON = ['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];
const fmtDate = (t) => { const d = new Date(t); return `${d.getDate()} ${MON[d.getMonth()]} ${d.getFullYear()}`; };
const fmtDT = (t) => { const d = new Date(t); let h = d.getHours(); const ap = h >= 12 ? 'PM' : 'AM'; h = h % 12 || 12; return `${fmtDate(t)}, ${h}:${String(d.getMinutes()).padStart(2,'0')} ${ap}`; };
const ago = (t) => { const m = Math.max(1, Math.round((Date.now() - t) / 6e4)); if (m < 60) return m + ' min ago'; const h = Math.round(m / 60); if (h < 24) return h + ' hr ago'; const d = Math.round(h / 24); return d + (d === 1 ? ' day ago' : ' days ago'); };

const ICONS = {
  drop: ['M12 22a7 7 0 0 0 7-7c0-2-1-3.9-3-5.5s-3.5-4-4-6.5c-.5 2.5-2 4.9-4 6.5C6 11.1 5 13 5 15a7 7 0 0 0 7 7z'],
  toilet: ['M7 3h10v6H7z','M5 9h14c0 5-2 8-5 9v3h-4v-3c-3-1-5-4-5-9z'],
  wash: ['M12 3l1.9 5.1L19 10l-5.1 1.9L12 17l-1.9-5.1L5 10l5.1-1.9z','M19 17v4','M17 19h4'],
  other: ['M12 2a10 10 0 1 0 0 20 10 10 0 0 0 0-20z','M12 8v4','M12 16h.01'],
  shield: ['M20 13c0 5-3.5 7.5-7.66 8.95a1 1 0 0 1-.67-.01C7.5 20.5 4 18 4 13V6a1 1 0 0 1 1-1c2 0 4.5-1.2 6.24-2.72a1.17 1.17 0 0 1 1.52 0C14.51 3.81 17 5 19 5a1 1 0 0 1 1 1z','m9 12 2 2 4-4'],
  user: ['M19 21v-2a4 4 0 0 0-4-4H9a4 4 0 0 0-4 4v2','M12 3a4 4 0 1 0 0 8 4 4 0 0 0 0-8z'],
  lock: ['M5 11h14v10H5z','M8 11V7a4 4 0 0 1 8 0v4'],
  out: ['M9 21H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h4','m16 17 5-5-5-5','M21 12H9'],
  plus: ['M5 12h14','M12 5v14'],
  dash: ['M3 3h7v9H3z','M14 3h7v5h-7z','M14 12h7v9h-7z','M3 16h7v5H3z'],
  list: ['M8 6h13','M8 12h13','M8 18h13','M3 6h.01','M3 12h.01','M3 18h.01'],
  search: ['m21 21-4.3-4.3','M11 3a8 8 0 1 0 0 16 8 8 0 0 0 0-16z'],
  upload: ['M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4','m17 8-5-5-5 5','M12 3v12'],
  x: ['M18 6 6 18','m6 6 12 12'],
  check: ['M20 6 9 17l-5-5'],
  clock: ['M12 2a10 10 0 1 0 0 20 10 10 0 0 0 0-20z','M12 6v6l4 2'],
  alert: ['m21.73 18-8-14a2 2 0 0 0-3.48 0l-8 14A2 2 0 0 0 4 21h16a2 2 0 0 0 1.73-3','M12 9v4','M12 17h.01'],
  wrench: ['M14.7 6.3a1 1 0 0 0 0 1.4l1.6 1.6a1 1 0 0 0 1.4 0l3.77-3.77a6 6 0 0 1-7.94 7.94l-6.91 6.91a2.12 2.12 0 0 1-3-3l6.91-6.91a6 6 0 0 1 7.94-7.94l-3.76 3.76z'],
  users: ['M16 21v-2a4 4 0 0 0-4-4H6a4 4 0 0 0-4 4v2','M9 3a4 4 0 1 0 0 8 4 4 0 0 0 0-8z','M22 21v-2a4 4 0 0 0-3-3.87','M16 3.13a4 4 0 0 1 0 7.75'],
  right: ['M5 12h14','m12 5 7 7-7 7'],
  left: ['m12 19-7-7 7-7','M19 12H5'],
  image: ['M5 3h14a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2z','m21 15-5-5L5 21','M9 8.5h.01'],
  building: ['M6 22V4a2 2 0 0 1 2-2h8a2 2 0 0 1 2 2v18z','M6 12H4a2 2 0 0 0-2 2v6a2 2 0 0 0 2 2h2','M18 9h2a2 2 0 0 1 2 2v9a2 2 0 0 1-2 2h-2','M10 6h4','M10 10h4','M10 14h4','M10 18h4'],
  menu: ['M4 6h16','M4 12h16','M4 18h16'],
  pin: ['M20 10c0 6-8 12-8 12s-8-6-8-12a8 8 0 0 1 16 0','M12 7a3 3 0 1 0 0 6 3 3 0 0 0 0-6z'],
  cal: ['M8 2v4','M16 2v4','M3 6h18v15H3z','M3 10h18'],
  note: ['M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z','M14 2v6h6','M8 13h8','M8 17h5'],
  inbox: ['M22 12h-6l-2 3h-4l-2-3H2','M5.45 5.11 2 12v6a2 2 0 0 0 2 2h16a2 2 0 0 0 2-2v-6l-3.45-6.89A2 2 0 0 0 16.76 4H7.24a2 2 0 0 0-1.79 1.11z'],
  eye: ['M2 12s3.5-7 10-7 10 7 10 7-3.5 7-10 7S2 12 2 12z','M12 9a3 3 0 1 0 0 6 3 3 0 0 0 0-6z'],
  info: ['M12 2a10 10 0 1 0 0 20 10 10 0 0 0 0-20z','M12 16v-4','M12 8h.01']
};
const Icon = ({ n, c = 'w-5 h-5', sw = 1.75 }) => html`<svg class=${c} viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width=${sw} stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">${(ICONS[n] || []).map((d, i) => html`<path key=${i} d=${d} />`)}</svg>`;
const CAT_ICON = { 'Drinking Water Problem': 'drop', 'Dirty Toilet': 'toilet', 'Hand-Wash Facility Problem': 'wash', 'Other Hygiene Issues': 'other' };

const Logo = ({ light, size = 'md' }) => html`
  <div class="flex items-center gap-3">
    <div class=${'grid place-items-center rounded-xl ' + (size === 'lg' ? 'w-12 h-12' : 'w-10 h-10') + (light ? ' bg-white/10 ring-1 ring-white/20' : ' bg-navy-900')}>
      <svg viewBox="0 0 32 32" class=${size === 'lg' ? 'w-7 h-7' : 'w-6 h-6'} fill="none"><path d="M16 4c3.2 4.6 7.5 8.1 7.5 13.2A7.5 7.5 0 0 1 16 24.7a7.5 7.5 0 0 1-7.5-7.5C8.5 12.1 12.8 8.6 16 4z" fill="#6FB9BA"/><path d="M11 18.5c1.6-1.2 3-1.2 4.5 0s3 1.2 5.5 0" stroke="#fff" stroke-width="1.6" stroke-linecap="round"/></svg>
    </div>
    <div class="leading-tight">
      <div class=${'font-serif font-semibold tracking-wide ' + (size === 'lg' ? 'text-2xl' : 'text-lg') + (light ? ' text-white' : ' text-navy-900')}>NEER NALAM</div>
      <div class=${'text-[10px] uppercase tracking-[.18em] ' + (light ? 'text-teal-300' : 'text-teal-600')}>Campus Hygiene</div>
    </div>
  </div>`;

const SM = {
  'NEW': { cls: 'bg-navy-100 text-navy-700 ring-navy-700/10', dot: 'bg-navy-700', note: 'Complaint received' },
  'REVIEWED': { cls: 'bg-teal-100 text-teal-700 ring-teal-700/10', dot: 'bg-teal-500', note: 'Reviewed by admin' },
  'IN PROGRESS': { cls: 'bg-amber-100 text-amber-800 ring-amber-800/10', dot: 'bg-amber-500', note: 'Work has started' },
  'RESOLVED': { cls: 'bg-emerald-100 text-emerald-800 ring-emerald-800/10', dot: 'bg-emerald-500', note: 'Problem has been fixed' }
};
const Badge = ({ s }) => html`<span class=${'inline-flex items-center gap-1.5 whitespace-nowrap rounded-full px-2.5 py-1 text-[11px] font-semibold tracking-wide ring-1 ring-inset ' + SM[s].cls}><span class=${'w-1.5 h-1.5 rounded-full ' + SM[s].dot}></span>${s}</span>`;
const Delayed = () => html`<span class="inline-flex items-center gap-1 whitespace-nowrap rounded-full bg-red-50 text-red-700 ring-1 ring-inset ring-red-700/10 px-2 py-1 text-[11px] font-semibold"><${Icon} n="alert" c="w-3 h-3" />Delayed</span>`;

const Btn = ({ kind = 'primary', children, class: cl = '', ...rest }) => {
  const k = { primary: 'bg-navy-900 text-white hover:bg-navy-700', teal: 'bg-teal-500 text-white hover:bg-teal-600', ghost: 'bg-white text-navy-900 ring-1 ring-inset ring-slate-200 hover:bg-slate-50', light: 'bg-white text-navy-900 hover:bg-teal-50' }[kind];
  return html`<button ...${rest} class=${'inline-flex items-center justify-center gap-2 rounded-xl px-4 py-2.5 text-sm font-semibold transition disabled:opacity-50 disabled:cursor-not-allowed ' + k + ' ' + cl}>${children}</button>`;
};

/* ---- app context: session + navigation ---- */
const Ctx = createContext(null);
const useApp = () => useContext(Ctx);

const Toast = ({ t }) => t ? html`<div role="status" class=${'fixed z-50 left-1/2 -translate-x-1/2 bottom-24 sm:bottom-6 fade-up rounded-xl px-4 py-3 text-sm font-medium shadow-lift flex items-center gap-2 ' + (t.err ? 'bg-red-700 text-white' : 'bg-navy-900 text-white')}><${Icon} n=${t.err ? 'alert' : 'check'} c="w-4 h-4" />${t.msg}</div>` : null;

const Lightbox = ({ src, onClose }) => !src ? null : html`
  <div class="fixed inset-0 z-50 bg-navy-950/80 grid place-items-center p-4" onClick=${onClose} role="dialog" aria-label="Photo preview">
    <div class="relative max-w-3xl w-full" onClick=${e => e.stopPropagation()}>
      <img src=${src} alt="Uploaded complaint photo" class="w-full max-h-[80vh] object-contain rounded-2xl bg-white" />
      <button onClick=${onClose} class="absolute -top-3 -right-3 w-9 h-9 grid place-items-center rounded-full bg-white text-navy-900 shadow-lift" aria-label="Close"><${Icon} n="x" c="w-4 h-4" /></button>
    </div>
  </div>`;

const Thumb = ({ src, onOpen, size = 'w-12 h-12' }) => src
  ? html`<button onClick=${() => onOpen(src)} class=${size + ' rounded-lg overflow-hidden ring-1 ring-slate-200 shrink-0 hover:ring-teal-400 transition'} aria-label="View photo"><img src=${src} alt="" class="w-full h-full object-cover" /></button>`
  : html`<div class=${size + ' rounded-lg bg-slate-100 grid place-items-center text-slate-400 shrink-0'}><${Icon} n="image" c="w-5 h-5" /></div>`;

/* ---- portal shell: top bar + side navigation ---- */
const Shell = ({ role, links, current, children }) => {
  const { session, nav, logout } = useApp(); const [open, setOpen] = useState(false);
  const isAdmin = role === 'ADMIN';
  const Nav = html`<nav class="flex flex-col gap-1">${links.map(l => html`
    <button key=${l.to} onClick=${() => { nav(l.to); setOpen(false); }} class=${'flex items-center gap-3 rounded-xl px-3.5 py-2.5 text-sm font-medium text-left transition ' + (current === l.to ? 'bg-white/10 text-white' : 'text-navy-100/70 hover:bg-white/5 hover:text-white')}>
      <${Icon} n=${l.icon} c="w-[18px] h-[18px]" />${l.label}${l.badge ? html`<span class="ml-auto rounded-full bg-teal-400 text-navy-900 text-[11px] font-bold px-2 py-0.5">${l.badge}</span>` : null}
    </button>`)}</nav>`;
  return html`
  <div class="min-h-screen lg:flex">
    <aside class=${'bg-navy-900 text-white lg:w-64 lg:shrink-0 lg:sticky lg:top-0 lg:h-screen lg:flex lg:flex-col ' + (open ? 'fixed inset-0 z-40 flex flex-col' : 'hidden lg:flex')}>
      <div class="px-5 pt-6 pb-5 flex items-center justify-between"><${Logo} light=${true} />
        <button class="lg:hidden w-9 h-9 grid place-items-center rounded-lg bg-white/10" onClick=${() => setOpen(false)} aria-label="Close menu"><${Icon} n="x" c="w-4 h-4" /></button></div>
      <div class="px-3 flex-1 overflow-y-auto">
        <div class="px-3.5 pb-2 text-[10px] uppercase tracking-[.18em] text-teal-300">${isAdmin ? 'Admin portal' : 'Student portal'}</div>${Nav}</div>
      <div class="m-3 rounded-2xl bg-white/5 p-4">
        <div class="flex items-center gap-3"><div class="w-9 h-9 rounded-full bg-teal-400 text-navy-900 grid place-items-center text-sm font-bold">${session.user.name.split(' ').filter(w => !w.endsWith('.')).map(w => w[0]).slice(0, 2).join('')}</div>
          <div class="min-w-0"><div class="text-sm font-semibold truncate">${session.user.name}</div><div class="text-xs text-navy-100/60 truncate">${isAdmin ? 'Administrator' : session.user.regNo}</div></div></div>
        <button onClick=${logout} class="mt-3 w-full flex items-center justify-center gap-2 rounded-lg bg-white/10 hover:bg-white/15 py-2 text-sm"><${Icon} n="out" c="w-4 h-4" />Sign out</button>
      </div>
    </aside>
    <div class="flex-1 min-w-0">
      <header class="lg:hidden sticky z-30 bg-navy-900 text-white gutter" style=${{top:"env(safe-area-inset-top,0px)"}}><div class="flex items-center justify-between py-3"><${Logo} light=${true} /><button class="w-10 h-10 grid place-items-center rounded-lg bg-white/10" onClick=${() => setOpen(true)} aria-label="Open menu"><${Icon} n="menu" /></button></div></header>
      <main class="gutter py-6 lg:py-9 lg:px-10 max-w-[1280px] mx-auto fade-up">${children}</main>
    </div>
  </div>`;
};

const PageHead = ({ title, sub, right }) => html`
  <div class="flex flex-wrap items-end justify-between gap-4 mb-7">
    <div class="min-w-0"><h1 class="font-serif text-[28px] sm:text-[32px] font-semibold text-navy-900 leading-tight">${title}</h1>${sub ? html`<p class="text-slate-500 mt-1.5 max-w-2xl">${sub}</p>` : null}</div>${right}
  </div>`;

const Stat = ({ label, value, icon, tone = 'navy', hint }) => {
  const t = { navy: 'bg-navy-100 text-navy-700', teal: 'bg-teal-100 text-teal-700', amber: 'bg-amber-100 text-amber-800', green: 'bg-emerald-100 text-emerald-800', red: 'bg-red-50 text-red-700' }[tone];
  return html`<div class="bg-white rounded-2xl shadow-soft p-5 ring-1 ring-slate-100">
    <div class="flex items-center justify-between"><span class="text-[13px] font-medium text-slate-500">${label}</span><span class=${'w-9 h-9 rounded-xl grid place-items-center ' + t}><${Icon} n=${icon} c="w-[18px] h-[18px]" /></span></div>
    <div class="mt-3 font-serif text-4xl font-semibold text-navy-900 tabular-nums">${value}</div>${hint ? html`<div class="text-xs text-slate-400 mt-1">${hint}</div>` : null}</div>`;
};

const Timeline = ({ items }) => html`
  <ol class="relative ml-2 border-l border-slate-200 space-y-5">${items.map((h, i) => html`
    <li key=${h.id} class="pl-6 relative">
      <span class=${'absolute -left-[7px] top-1 w-3.5 h-3.5 rounded-full ring-4 ring-white ' + (h.kind === 'status' ? SM[h.next].dot : h.kind === 'assign' ? 'bg-navy-700' : 'bg-slate-400')}></span>
      <div class="text-sm font-semibold text-navy-900">${h.kind === 'status' ? (h.prev ? `${h.prev} → ${h.next}` : `Complaint submitted (${h.next})`) : h.kind === 'assign' ? (h.next ? `Assigned to ${TEAMS.find(t => t.id === h.next).name}` : 'Assignment removed') : 'Internal note added'}</div>
      <div class="text-xs text-slate-500 mt-0.5">${fmtDT(h.at)} · ${h.by}</div>
    </li>`)}</ol>`;

/* ================= PUBLIC PAGES ================= */
const Landing = () => {
  const { nav } = useApp();
  const problems = [
    { icon: 'drop', t: 'Unsafe Drinking Water', d: 'Cloudy, smelly or unavailable drinking water, and dispensers or RO units that are out of order.' },
    { icon: 'toilet', t: 'Dirty Toilets', d: 'Washrooms that need cleaning, broken flushes, leaking taps and missing supplies.' },
    { icon: 'wash', t: 'No Hand-Wash Facilities', d: 'Wash stations without water or soap, especially near canteens and washrooms.' }
  ];
  const steps = [['Report', 'Log in, pick a category, add a photo and the exact location.'], ['Review', 'The hygiene office checks the photo and description and assigns a team.'], ['Fix', 'Maintenance works on the issue while status updates appear in your account.'], ['Confirm', 'You see the resolved status and the full progress history.']];
  return html`
  <div>
    <section class="hero-bg text-white">
      <div class="gutter"><div class="max-w-[1180px] mx-auto">
        <div class="flex items-center justify-between py-5"><${Logo} light=${true} />
          <div class="hidden sm:flex gap-2"><${Btn} kind="ghost" class="!bg-white/10 !text-white !ring-white/20 hover:!bg-white/15" onClick=${() => nav('/student/login')}>Student Portal<//><${Btn} kind="light" onClick=${() => nav('/admin/login')}>Admin Portal<//></div></div>
        <div class="grid lg:grid-cols-[1.15fr_.85fr] gap-10 items-center py-14 sm:py-20">
          <div class="fade-up">
            <span class="inline-flex items-center gap-2 rounded-full bg-white/10 ring-1 ring-white/15 px-3 py-1 text-xs tracking-wide text-teal-200"><${Icon} n="shield" c="w-3.5 h-3.5" />Campus hygiene management system</span>
            <h1 class="font-serif text-[40px] sm:text-6xl font-semibold leading-[1.05] mt-5">Clean Water.<br /><span class="text-teal-300">Healthy Campus.</span></h1>
            <p class="mt-5 text-lg text-navy-100/80 max-w-xl leading-relaxed">NEER NALAM gives every student a direct way to report unsafe water, dirty toilets and missing hand-wash facilities, and gives the administration one place to assign work, track progress and close each issue.</p>
            <div class="mt-8 flex flex-wrap gap-3"><${Btn} kind="teal" class="!py-3 !px-5" onClick=${() => nav('/student/login')}><${Icon} n="user" c="w-4 h-4" />Student Portal<//><${Btn} kind="light" class="!py-3 !px-5" onClick=${() => nav('/admin/login')}><${Icon} n="lock" c="w-4 h-4" />Admin Portal<//></div>
          </div>
          <div class="fade-up" style=${{animationDelay:".12s"}}>
            <div class="rounded-3xl bg-white text-navy-900 shadow-lift p-5 sm:p-6">
              <div class="flex items-center justify-between"><div class="text-xs font-semibold text-slate-400 uppercase tracking-wider">Sample complaint</div><${Badge} s="IN PROGRESS" /></div>
              <div class="mt-3 font-serif text-xl font-semibold">Washroom cleaning required</div>
              <div class="text-sm text-slate-500 mt-1 flex items-center gap-1.5"><${Icon} n="pin" c="w-4 h-4" />Block B, First Floor</div>
              <div class="mt-5 space-y-3.5 text-sm">${[['Complaint received', 'NEW', true], ['Reviewed by admin', 'REVIEWED', true], ['Housekeeping assigned', 'IN PROGRESS', true], ['Problem resolved', 'RESOLVED', false]].map(([l, s, done]) => html`
                <div key=${l} class="flex items-center gap-3"><span class=${'w-6 h-6 rounded-full grid place-items-center ' + (done ? 'bg-teal-500 text-white' : 'bg-slate-100 text-slate-300')}><${Icon} n="check" c="w-3.5 h-3.5" sw=${2.5} /></span><span class=${done ? 'font-medium' : 'text-slate-400'}>${l}</span></div>`)}</div>
            </div>
          </div>
        </div>
      </div></div>
    </section>

    <section class="gutter py-16"><div class="max-w-[1180px] mx-auto">
      <div class="max-w-2xl"><div class="text-xs uppercase tracking-[.18em] text-teal-600 font-semibold">What we address</div><h2 class="font-serif text-3xl sm:text-4xl font-semibold mt-2">Three problems that affect every student</h2></div>
      <div class="grid md:grid-cols-3 gap-5 mt-9">${problems.map(p => html`
        <div key=${p.t} class="bg-white rounded-2xl shadow-soft ring-1 ring-slate-100 p-6 hover:shadow-lift hover:-translate-y-0.5 transition">
          <div class="w-12 h-12 rounded-xl bg-teal-100 text-teal-700 grid place-items-center"><${Icon} n=${p.icon} c="w-6 h-6" /></div>
          <h3 class="font-serif text-xl font-semibold mt-5">${p.t}</h3><p class="text-slate-500 mt-2 leading-relaxed">${p.d}</p></div>`)}</div>
    </div></section>

    <section class="bg-white border-y border-slate-100 gutter py-16"><div class="max-w-[1180px] mx-auto">
      <div class="max-w-2xl"><div class="text-xs uppercase tracking-[.18em] text-teal-600 font-semibold">How a complaint moves</div><h2 class="font-serif text-3xl sm:text-4xl font-semibold mt-2">From report to resolution</h2></div>
      <ol class="grid sm:grid-cols-2 lg:grid-cols-4 gap-5 mt-9">${steps.map(([t, d], i) => html`
        <li key=${t} class="rounded-2xl bg-navy-50 p-5"><div class="w-8 h-8 rounded-full bg-navy-900 text-white grid place-items-center text-sm font-semibold">${i + 1}</div><h3 class="font-semibold mt-4">${t}</h3><p class="text-sm text-slate-500 mt-1.5 leading-relaxed">${d}</p></li>`)}</ol>
    </div></section>

    <section class="gutter py-16"><div class="max-w-[1180px] mx-auto grid md:grid-cols-2 gap-5">
      ${[['Student Portal', 'user', 'Report a problem, upload a photo and follow progress on your own complaints.', ['Submit and track your complaints', 'See progress history', 'Your complaints stay private'], '/student/login', 'Student sign in'],
         ['Admin Portal', 'lock', 'Review every complaint, assign maintenance teams and update status.', ['View and filter all complaints', 'Assign teams, add internal notes', 'Spot pending and delayed issues'], '/admin/login', 'Admin sign in']].map(([t, ic, d, li, to, cta]) => html`
        <div key=${t} class="bg-white rounded-2xl shadow-soft ring-1 ring-slate-100 p-7">
          <div class="flex items-center gap-3"><span class="w-11 h-11 rounded-xl bg-navy-900 text-white grid place-items-center"><${Icon} n=${ic} /></span><h3 class="font-serif text-2xl font-semibold">${t}</h3></div>
          <p class="text-slate-500 mt-3">${d}</p>
          <ul class="mt-4 space-y-2 text-sm">${li.map(x => html`<li key=${x} class="flex items-center gap-2"><span class="text-teal-500"><${Icon} n="check" c="w-4 h-4" sw=${2.25} /></span>${x}</li>`)}</ul>
          <${Btn} class="mt-6" onClick=${() => nav(to)}>${cta}<${Icon} n="right" c="w-4 h-4" /><//></div>`)}
    </div></section>

    <footer class="bg-navy-900 text-navy-100/70 gutter py-8 text-sm"><div class="max-w-[1180px] mx-auto flex flex-wrap items-center justify-between gap-3"><${Logo} light=${true} /><span>Clean Water. Healthy Campus.</span></div></footer>
  </div>`;
};

const LoginPage = ({ role }) => {
  const { nav, signIn, flash } = useApp();
  const isAdmin = role === 'ADMIN';
  const [id, setId] = useState(''); const [pw, setPw] = useState(''); const [err, setErr] = useState(''); const [busy, setBusy] = useState(false);
  const demo = isAdmin ? [['admin.hygiene', 'Dr. Meera Iyer'], ['admin.facilities', 'Suresh Nair']] : [['21CS1042', 'Ananya Krishnan'], ['21EC2017', 'Rohan Mehta'], ['22ME3008', 'Divya Raman']];
  const submit = async (e) => {
    e.preventDefault(); setErr(''); setBusy(true);
    try { await signIn(role, id, pw); } catch (x) { setErr(x.message); setBusy(false); }
  };
  return html`
  <div class="min-h-screen lg:grid lg:grid-cols-[.9fr_1.1fr]">
    <div class="hero-bg text-white gutter py-8 lg:py-12 lg:flex lg:flex-col lg:justify-between">
      <${Logo} light=${true} />
      <div class="hidden lg:block max-w-md"><h2 class="font-serif text-4xl font-semibold leading-tight">${isAdmin ? 'Administration console' : 'Your voice for a cleaner campus'}</h2>
        <p class="mt-4 text-navy-100/75 leading-relaxed">${isAdmin ? 'Authorised hygiene and facilities staff can review, assign and resolve campus complaints.' : 'Report water, toilet and hand-wash problems and follow every update until they are fixed.'}</p></div>
      <div class="hidden lg:block text-sm text-navy-100/50">Clean Water. Healthy Campus.</div>
    </div>
    <div class="gutter py-10 lg:py-12 grid place-items-center"><div class="w-full max-w-md fade-up">
      <button onClick=${() => nav('/')} class="text-sm text-slate-500 hover:text-navy-900 inline-flex items-center gap-1.5 mb-6"><${Icon} n="left" c="w-4 h-4" />Back to home</button>
      <div class="flex items-center gap-2 text-xs uppercase tracking-[.18em] text-teal-600 font-semibold"><${Icon} n=${isAdmin ? 'lock' : 'user'} c="w-4 h-4" />${isAdmin ? 'Admin portal' : 'Student portal'}</div>
      <h1 class="font-serif text-3xl font-semibold mt-2">${isAdmin ? 'Admin sign in' : 'Student sign in'}</h1>
      <form onSubmit=${submit} class="mt-7 space-y-4 bg-white rounded-2xl shadow-soft ring-1 ring-slate-100 p-6">
        <div><label for="login-id" class="text-sm font-medium">${isAdmin ? 'Admin Username' : 'Register Number'}</label>
          <input id="login-id" value=${id} onInput=${e => setId(e.target.value)} required autocomplete="username" placeholder=${isAdmin ? 'e.g. admin.hygiene' : 'e.g. 21CS1042'} class="mt-1.5 w-full rounded-xl border border-slate-200 px-3.5 py-2.5 focus:border-teal-500 outline-none" /></div>
        <div><label for="login-pw" class="text-sm font-medium">Password</label>
          <input id="login-pw" type="password" value=${pw} onInput=${e => setPw(e.target.value)} required autocomplete="current-password" class="mt-1.5 w-full rounded-xl border border-slate-200 px-3.5 py-2.5 focus:border-teal-500 outline-none" /></div>
        ${err ? html`<div role="alert" class="flex items-start gap-2 rounded-xl bg-red-50 text-red-700 text-sm px-3.5 py-2.5"><${Icon} n="alert" c="w-4 h-4 mt-0.5 shrink-0" />${err}</div>` : null}
        <${Btn} type="submit" class="w-full !py-3" disabled=${busy}>${busy ? 'Signing in…' : 'Sign in'}<//>
      </form>
      <div class="mt-5 rounded-2xl bg-teal-50 ring-1 ring-teal-100 p-4 text-sm">
        <div class="font-semibold text-teal-700 flex items-center gap-1.5"><${Icon} n="info" c="w-4 h-4" />Demo accounts</div>
        <p class="text-slate-500 mt-1">Password for all demo accounts: <code class="font-semibold text-navy-900">${isAdmin ? 'Admin@123' : 'Student@123'}</code>. Tap one to fill the form.</p>
        <div class="flex flex-wrap gap-2 mt-3">${demo.map(([u, n]) => html`<button key=${u} type="button" onClick=${() => { setId(u); setPw(isAdmin ? 'Admin@123' : 'Student@123'); }} class="rounded-lg bg-white ring-1 ring-teal-200 px-2.5 py-1.5 text-left hover:ring-teal-500"><span class="block text-xs font-semibold text-navy-900">${u}</span><span class="block text-[11px] text-slate-500">${n}</span></button>`)}</div>
      </div>
      <p class="text-xs text-slate-400 mt-5 text-center">${isAdmin ? 'Student accounts cannot sign in here.' : 'Administrators sign in through the Admin Portal.'}</p>
    </div></div>
  </div>`;
};

const Denied = ({ reason }) => {
  const { session, nav } = useApp();
  const home = session ? (session.user.role === 'ADMIN' ? '/admin' : '/student') : '/';
  return html`<div class="min-h-screen grid place-items-center gutter py-12"><div class="max-w-md text-center bg-white rounded-3xl shadow-lift ring-1 ring-slate-100 p-9 fade-up">
    <div class="w-14 h-14 mx-auto rounded-2xl bg-red-50 text-red-700 grid place-items-center"><${Icon} n="lock" c="w-7 h-7" /></div>
    <h1 class="font-serif text-3xl font-semibold mt-5">Access denied</h1>
    <p class="text-slate-500 mt-3 leading-relaxed">${reason || 'Your account does not have permission to open this page.'}</p>
    <${Btn} class="mt-6" onClick=${() => nav(home)}>${session ? (session.user.role === 'ADMIN' ? 'Go to Admin Dashboard' : 'Go to Student Dashboard') : 'Back to home'}<//></div></div>`;
};

/* Demo-mode notice + route tester (attempt to open any URL, guards decide) */
const DemoDock = () => {
  const { nav, path } = useApp(); const [open, setOpen] = useState(false); const [v, setV] = useState('/admin');
  return html`<div class="fixed z-40 left-3 sm:left-4" style=${{bottom:"max(12px,env(safe-area-inset-bottom,0px))"}}>
    ${open ? html`<div class="fade-up mb-2 w-[min(320px,calc(100vw-24px))] rounded-2xl bg-white shadow-lift ring-1 ring-slate-200 p-4 text-sm">
      <div class="font-semibold flex items-center gap-1.5"><${Icon} n="info" c="w-4 h-4 text-teal-600" />Demonstration mode</div>
      <p class="text-slate-500 mt-1.5 leading-relaxed text-[13px]">No live database is connected. Sample data is held in this browser tab only and resets when the page reloads. Open this page in two tabs to watch status changes sync between the portals.</p>
      <div class="mt-3 text-xs font-semibold text-slate-400 uppercase tracking-wider">Test route protection</div>
      <form class="mt-1.5 flex gap-2" onSubmit=${e => { e.preventDefault(); nav(v); setOpen(false); }}><label class="sr-only" for="route-test">Route</label><input id="route-test" value=${v} onInput=${e => setV(e.target.value)} class="min-w-0 flex-1 rounded-lg border border-slate-200 px-2.5 py-1.5 text-sm" /><${Btn} type="submit" class="!py-1.5 !px-3">Go<//></form>
      <div class="flex flex-wrap gap-1.5 mt-2">${['/admin', '/admin/maintenance', '/student'].map(r => html`<button key=${r} onClick=${() => setV(r)} class="rounded-md bg-slate-100 px-2 py-1 text-xs hover:bg-teal-100">${r}</button>`)}</div></div>` : null}
    <button onClick=${() => setOpen(!open)} class="flex items-center gap-2 rounded-full bg-navy-900 text-white pl-3 pr-3.5 py-2 text-xs font-semibold shadow-lift"><span class="w-2 h-2 rounded-full bg-amber-400"></span>Demo mode</button></div>`;
};

/* ================= STUDENT PORTAL ================= */
const STU_LINKS = [{ to: '/student', label: 'Dashboard', icon: 'dash' }, { to: '/student/report', label: 'Report a Problem', icon: 'plus' }, { to: '/student/complaints', label: 'My Complaints', icon: 'list' }];
const useStudentData = () => { useDB(); const { session } = useApp(); try { return api.studentList(session.token); } catch (e) { return []; } };

const StudentShell = ({ current, children }) => html`<${Shell} role="STUDENT" links=${STU_LINKS} current=${current}>${children}<//>`;

const ComplaintCard = ({ c }) => {
  const { nav, openPhoto } = useApp();
  return html`<div class="bg-white rounded-2xl shadow-soft ring-1 ring-slate-100 p-4 flex gap-4 hover:shadow-lift transition">
    <${Thumb} src=${c.photo} onOpen=${openPhoto} size="w-20 h-20 sm:w-24 sm:h-24" />
    <div class="min-w-0 flex-1">
      <div class="flex flex-wrap items-center justify-between gap-2"><span class="text-xs font-semibold text-slate-400 tabular-nums">${c.id}</span><${Badge} s=${c.status} /></div>
      <div class="font-semibold mt-1 flex items-center gap-2"><span class="text-teal-600"><${Icon} n=${CAT_ICON[c.category]} c="w-4 h-4" /></span>${c.category}</div>
      <div class="text-sm text-slate-500 mt-1 flex items-start gap-1.5"><${Icon} n="pin" c="w-4 h-4 mt-0.5 shrink-0" /><span class="min-w-0">${c.building}, ${c.floor}, ${c.room}</span></div>
      <div class="flex items-center justify-between mt-2.5"><span class="text-xs text-slate-400">Submitted ${fmtDate(c.submittedAt)}</span>
        <button onClick=${() => nav('/student/complaints/' + c.id)} class="text-sm font-semibold text-navy-700 hover:text-teal-600 inline-flex items-center gap-1">View progress<${Icon} n="right" c="w-4 h-4" /></button></div>
    </div></div>`;
};

const StudentDashboard = () => {
  const { session, nav } = useApp(); const list = useStudentData();
  const n = (...s) => list.filter(c => s.includes(c.status)).length;
  return html`<${StudentShell} current="/student">
    <${PageHead} title=${'Welcome, ' + session.user.name.split(' ')[0]} sub=${'Register No. ' + session.user.regNo + '. Report hygiene problems around campus and follow each one until it is fixed.'} right=${html`<${Btn} onClick=${() => nav('/student/report')}><${Icon} n="plus" c="w-4 h-4" />Report a Problem<//>`} />
    <div class="grid grid-cols-2 xl:grid-cols-4 gap-4">
      <${Stat} label="Total submitted" value=${list.length} icon="note" tone="navy" />
      <${Stat} label="New" value=${n('NEW')} icon="inbox" tone="navy" hint="Awaiting review" />
      <${Stat} label="In progress" value=${n('REVIEWED', 'IN PROGRESS')} icon="wrench" tone="amber" hint="Reviewed or being fixed" />
      <${Stat} label="Resolved" value=${n('RESOLVED')} icon="check" tone="green" />
    </div>
    <div class="flex items-center justify-between mt-10 mb-4"><h2 class="font-serif text-2xl font-semibold">Recent complaints</h2><button onClick=${() => nav('/student/complaints')} class="text-sm font-semibold text-navy-700 hover:text-teal-600">View all</button></div>
    ${list.length ? html`<div class="grid lg:grid-cols-2 gap-4">${list.slice(0, 4).map(c => html`<${ComplaintCard} key=${c.id} c=${c} />`)}</div>` : html`<${Empty} />`}
  <//>`;
};

const Empty = () => { const { nav } = useApp(); return html`<div class="bg-white rounded-2xl ring-1 ring-slate-100 shadow-soft p-10 text-center"><div class="w-12 h-12 mx-auto rounded-xl bg-teal-100 text-teal-700 grid place-items-center"><${Icon} n="inbox" c="w-6 h-6" /></div><h3 class="font-serif text-xl font-semibold mt-4">No complaints yet</h3><p class="text-slate-500 mt-1">Report a hygiene problem and it will appear here with live progress.</p><${Btn} class="mt-5" onClick=${() => nav('/student/report')}>Report a Problem<//></div>`; };

const FLOORS = ['Ground Floor', 'First Floor', 'Second Floor', 'Third Floor', 'Fourth Floor', 'Basement'];
const BUILDINGS = ['Block A (CSE)', 'Block B (Mechanical)', 'Block C (Civil)', 'Central Library', 'Main Canteen', 'Seminar Hall Complex', 'Hostel Block 1', 'Hostel Block 2', 'Sports Complex'];
const today = () => new Date().toISOString().slice(0, 10);

const ReportForm = () => {
  const { session, nav, flash } = useApp();
  const [f, setF] = useState({ category: '', building: '', floor: '', room: '', description: '', problemDate: today() });
  const [photoUrl, setPhotoUrl] = useState(null); const [fileName, setFileName] = useState(''); const [photoErr, setPhotoErr] = useState('');
  const [errs, setErrs] = useState({}); const [busy, setBusy] = useState(false); const [done, setDone] = useState(null); const [drag, setDrag] = useState(false);
  const set = (k, v) => setF(p => ({ ...p, [k]: v }));
  const pick = (file) => {
    setPhotoErr(''); if (!file) return;
    if (!['image/jpeg', 'image/png'].includes(file.type)) { setPhotoErr('Only JPG, JPEG and PNG images are supported.'); return; }
    if (file.size > 5 * 1024 * 1024) { setPhotoErr('Image is larger than 5 MB. Choose a smaller photo.'); return; }
    const r = new FileReader(); r.onload = () => { setPhotoUrl(r.result); setFileName(file.name); }; r.readAsDataURL(file);
  };
  const submit = async (e) => {
    e.preventDefault(); const er = {};
    if (!f.category) er.category = 'Choose a category.'; if (!f.building.trim()) er.building = 'Enter the building.'; if (!f.floor) er.floor = 'Choose a floor.';
    if (!f.room.trim()) er.room = 'Enter the room or facility.'; if (f.description.trim().length < 15) er.description = 'Describe the problem in at least 15 characters.'; if (!f.problemDate) er.problemDate = 'Choose the date.';
    setErrs(er); if (Object.keys(er).length) return;
    setBusy(true);
    try { const c = await api.studentCreate(session.token, { ...f, photo: photoUrl }); setDone(c); } catch (x) { flash(x.message, true); }
    setBusy(false);
  };
  const Err = ({ k }) => errs[k] ? html`<p class="text-xs text-red-600 mt-1">${errs[k]}</p>` : null;
  const inp = 'mt-1.5 w-full rounded-xl border border-slate-200 bg-white px-3.5 py-2.5 focus:border-teal-500 outline-none';

  if (done) return html`<${StudentShell} current="/student/report"><div class="max-w-xl mx-auto bg-white rounded-3xl shadow-lift ring-1 ring-slate-100 p-8 text-center fade-up">
    <div class="w-16 h-16 mx-auto rounded-full bg-emerald-100 text-emerald-700 grid place-items-center"><${Icon} n="check" c="w-8 h-8" sw=${2.25} /></div>
    <h1 class="font-serif text-3xl font-semibold mt-5">Complaint submitted</h1>
    <p class="text-slate-500 mt-2">Your report has been saved and is now visible to the hygiene office.</p>
    <div class="mt-6 rounded-2xl bg-navy-50 p-5"><div class="text-xs uppercase tracking-wider text-slate-500">Complaint ID</div><div class="font-serif text-3xl font-semibold text-navy-900 tabular-nums mt-1">${done.id}</div><div class="mt-2"><${Badge} s="NEW" /></div></div>
    <div class="mt-6 flex flex-wrap justify-center gap-3"><${Btn} onClick=${() => nav('/student/complaints/' + done.id)}>Track this complaint<//><${Btn} kind="ghost" onClick=${() => { setDone(null); setF({ category: '', building: '', floor: '', room: '', description: '', problemDate: today() }); setPhotoUrl(null); setFileName(''); }}>Report another<//></div></div><//>`;

  return html`<${StudentShell} current="/student/report">
    <${PageHead} title="Report a Problem" sub="Give as much detail as you can. A clear photo and exact location help the team fix it faster." />
    <form onSubmit=${submit} class="grid lg:grid-cols-[1fr_340px] gap-6 items-start" noValidate>
      <div class="space-y-6 min-w-0">
        <section class="bg-white rounded-2xl shadow-soft ring-1 ring-slate-100 p-5 sm:p-6">
          <h2 class="font-semibold">1. Problem category</h2>
          <div class="grid sm:grid-cols-2 gap-3 mt-4" role="radiogroup" aria-label="Problem category">${CATS.map(c => html`
            <label key=${c} class=${'flex items-center gap-3 rounded-xl p-3.5 cursor-pointer ring-1 transition ' + (f.category === c ? 'bg-teal-50 ring-teal-500' : 'ring-slate-200 hover:ring-teal-300')}>
              <input type="radio" name="category" class="sr-only" checked=${f.category === c} onChange=${() => set('category', c)} />
              <span class=${'w-10 h-10 rounded-lg grid place-items-center shrink-0 ' + (f.category === c ? 'bg-teal-500 text-white' : 'bg-slate-100 text-slate-500')}><${Icon} n=${CAT_ICON[c]} /></span><span class="text-sm font-medium">${c}</span></label>`)}</div><${Err} k="category" />
        </section>
        <section class="bg-white rounded-2xl shadow-soft ring-1 ring-slate-100 p-5 sm:p-6">
          <h2 class="font-semibold">2. Location</h2>
          <div class="grid sm:grid-cols-2 gap-4 mt-4">
            <div><label for="f-building" class="text-sm font-medium">Building name</label><input id="f-building" list="bl" value=${f.building} onInput=${e => set('building', e.target.value)} placeholder="e.g. Block A (CSE)" class=${inp} /><datalist id="bl">${BUILDINGS.map(b => html`<option key=${b} value=${b} />`)}</datalist><${Err} k="building" /></div>
            <div><label for="f-floor" class="text-sm font-medium">Floor</label><select id="f-floor" value=${f.floor} onChange=${e => set('floor', e.target.value)} class=${inp}><option value="">Select floor</option>${FLOORS.map(x => html`<option key=${x}>${x}</option>`)}</select><${Err} k="floor" /></div>
            <div class="sm:col-span-2"><label for="f-room" class="text-sm font-medium">Room number / Facility location</label><input id="f-room" value=${f.room} onInput=${e => set('room', e.target.value)} placeholder="e.g. Water dispenser near Lab 2" class=${inp} /><${Err} k="room" /></div>
          </div>
        </section>
        <section class="bg-white rounded-2xl shadow-soft ring-1 ring-slate-100 p-5 sm:p-6">
          <h2 class="font-semibold">3. Problem details</h2>
          <div class="mt-4 space-y-4">
            <div><label for="f-desc" class="text-sm font-medium">Problem description</label><textarea id="f-desc" rows="4" value=${f.description} onInput=${e => set('description', e.target.value)} placeholder="Example: Drinking water is dirty and the water dispenser is not working." class=${inp}></textarea><${Err} k="description" /></div>
            <div class="sm:max-w-xs"><label for="f-date" class="text-sm font-medium">Problem date</label><input id="f-date" type="date" max=${today()} value=${f.problemDate} onInput=${e => set('problemDate', e.target.value)} class=${inp} /><${Err} k="problemDate" /></div>
          </div>
        </section>
      </div>
      <aside class="space-y-6 lg:sticky lg:top-6">
        <section class="bg-white rounded-2xl shadow-soft ring-1 ring-slate-100 p-5 sm:p-6">
          <h2 class="font-semibold">Photo <span class="text-slate-400 font-normal">(optional)</span></h2>
          ${photoUrl ? html`<div class="mt-4"><img src=${photoUrl} alt="Selected photo preview" class="w-full aspect-[4/3] object-cover rounded-xl ring-1 ring-slate-200" /><div class="flex items-center justify-between gap-2 mt-3"><span class="text-xs text-slate-500 truncate min-w-0">${fileName}</span><button type="button" onClick=${() => { setPhotoUrl(null); setFileName(''); }} class="text-xs font-semibold text-red-700 shrink-0">Remove</button></div></div>`
            : html`<label for="f-photo" onDragOver=${e => { e.preventDefault(); setDrag(true); }} onDragLeave=${() => setDrag(false)} onDrop=${e => { e.preventDefault(); setDrag(false); pick(e.dataTransfer.files[0]); }} class=${'mt-4 flex flex-col items-center text-center gap-2 rounded-xl border-2 border-dashed p-7 cursor-pointer transition ' + (drag ? 'border-teal-500 bg-teal-50' : 'border-slate-200 hover:border-teal-400')}>
              <span class="w-11 h-11 rounded-xl bg-teal-100 text-teal-700 grid place-items-center"><${Icon} n="upload" /></span><span class="text-sm font-medium">Upload from your device</span><span class="text-xs text-slate-400">JPG, JPEG or PNG, up to 5 MB</span></label>`}
          <input id="f-photo" type="file" accept="image/jpeg,image/png,.jpg,.jpeg,.png" class="sr-only" onChange=${e => { pick(e.target.files[0]); e.target.value = ''; }} />
          ${photoErr ? html`<p class="text-xs text-red-600 mt-2" role="alert">${photoErr}</p>` : null}
        </section>
        <${Btn} type="submit" class="w-full !py-3.5" disabled=${busy}>${busy ? 'Submitting…' : 'Submit Complaint'}<${Icon} n="right" c="w-4 h-4" /><//>
      </aside>
    </form><//>`;
};

const MyComplaints = () => {
  const list = useStudentData(); const [flt, setFlt] = useState('ALL');
  const shown = list.filter(c => flt === 'ALL' || c.status === flt || (flt === 'IN PROGRESS' && c.status === 'REVIEWED'));
  return html`<${StudentShell} current="/student/complaints">
    <${PageHead} title="My Complaints" sub="Only complaints submitted from your account are shown here." />
    <div class="flex flex-wrap gap-2 mb-5">${['ALL', 'NEW', 'IN PROGRESS', 'RESOLVED'].map(s => html`<button key=${s} onClick=${() => setFlt(s)} class=${'rounded-full px-4 py-1.5 text-sm font-medium transition ' + (flt === s ? 'bg-navy-900 text-white' : 'bg-white ring-1 ring-slate-200 hover:ring-teal-400')}>${s === 'ALL' ? 'All' : s[0] + s.slice(1).toLowerCase()}</button>`)}</div>
    ${shown.length ? html`<div class="grid lg:grid-cols-2 gap-4">${shown.map(c => html`<${ComplaintCard} key=${c.id} c=${c} />`)}</div>` : list.length ? html`<p class="text-slate-500">No complaints with this status.</p>` : html`<${Empty} />`}
  <//>`;
};

const StudentDetail = ({ id }) => {
  useDB(); const { session, nav, openPhoto } = useApp(); let c, bad = '';
  try { c = api.studentGet(session.token, id); } catch (e) { bad = e.message; }
  if (bad) return html`<${StudentShell} current="/student/complaints"><div class="bg-white rounded-2xl shadow-soft p-10 text-center"><h1 class="font-serif text-2xl font-semibold">${bad}</h1><p class="text-slate-500 mt-2">This complaint does not exist or was not submitted from your account.</p><${Btn} class="mt-5" onClick=${() => nav('/student/complaints')}>Back to My Complaints<//></div><//>`;
  const steps = [['Received', ['NEW', 'REVIEWED', 'IN PROGRESS', 'RESOLVED']], ['Reviewed', ['REVIEWED', 'IN PROGRESS', 'RESOLVED']], ['In progress', ['IN PROGRESS', 'RESOLVED']], ['Resolved', ['RESOLVED']]];
  const last = c.history[c.history.length - 1];
  return html`<${StudentShell} current="/student/complaints">
    <button onClick=${() => nav('/student/complaints')} class="text-sm text-slate-500 hover:text-navy-900 inline-flex items-center gap-1.5 mb-4"><${Icon} n="left" c="w-4 h-4" />My Complaints</button>
    <${PageHead} title=${c.category} sub=${'Complaint ' + c.id} right=${html`<${Badge} s=${c.status} />`} />
    <div class="bg-white rounded-2xl shadow-soft ring-1 ring-slate-100 p-5 sm:p-6 mb-6">
      <div class="flex items-center justify-between"><h2 class="font-semibold">Latest progress</h2><span class="text-xs text-slate-400">Updated ${ago(last.at)}</span></div>
      <p class="text-slate-500 text-sm mt-1">${SM[c.status].note}.</p>
      <ol class="grid grid-cols-4 gap-2 mt-5">${steps.map(([l, ok]) => { const on = ok.includes(c.status); return html`<li key=${l} class="text-center"><div class=${'h-1.5 rounded-full ' + (on ? 'bg-teal-500' : 'bg-slate-200')}></div><div class=${'text-[11px] sm:text-xs mt-2 font-medium ' + (on ? 'text-navy-900' : 'text-slate-400')}>${l}</div></li>`; })}</ol>
    </div>
    <div class="grid lg:grid-cols-[1.1fr_.9fr] gap-6 items-start">
      <div class="bg-white rounded-2xl shadow-soft ring-1 ring-slate-100 p-5 sm:p-6 min-w-0">
        ${c.photo ? html`<button onClick=${() => openPhoto(c.photo)} class="block w-full"><img src=${c.photo} alt="Uploaded complaint photo" class="w-full max-h-80 object-cover rounded-xl ring-1 ring-slate-200" /></button>` : null}
        <dl class="grid sm:grid-cols-2 gap-x-6 gap-y-4 mt-5 text-sm">
          <div><dt class="text-slate-400 text-xs uppercase tracking-wider">Complaint ID</dt><dd class="font-semibold tabular-nums mt-0.5">${c.id}</dd></div>
          <div><dt class="text-slate-400 text-xs uppercase tracking-wider">Submitted</dt><dd class="font-semibold mt-0.5">${fmtDT(c.submittedAt)}</dd></div>
          <div><dt class="text-slate-400 text-xs uppercase tracking-wider">Location</dt><dd class="font-semibold mt-0.5">${c.building}, ${c.floor}, ${c.room}</dd></div>
          <div><dt class="text-slate-400 text-xs uppercase tracking-wider">Problem date</dt><dd class="font-semibold mt-0.5">${fmtDate(c.problemDate)}</dd></div>
          <div class="sm:col-span-2"><dt class="text-slate-400 text-xs uppercase tracking-wider">Description</dt><dd class="mt-0.5 leading-relaxed">${c.description}</dd></div>
        </dl></div>
      <div class="bg-white rounded-2xl shadow-soft ring-1 ring-slate-100 p-5 sm:p-6"><h2 class="font-semibold mb-5">Progress history</h2><${Timeline} items=${[...c.history].reverse()} /></div>
    </div><//>`;
};

/* ================= ADMIN PORTAL ================= */
const useAdminData = () => { useDB(); const { session } = useApp(); try { return api.adminList(session.token); } catch (e) { return []; } };
const AdminShell = ({ current, children }) => {
  const list = useAdminData(); const unassigned = list.filter(c => !c.team && c.status !== 'RESOLVED').length;
  const links = [{ to: '/admin', label: 'Dashboard', icon: 'dash' }, { to: '/admin/maintenance', label: 'Maintenance', icon: 'wrench', badge: unassigned || null }];
  return html`<${Shell} role="ADMIN" links=${links} current=${current}>${children}<//>`;
};
const teamName = (id) => id ? TEAMS.find(t => t.id === id).name : null;
const sel = 'rounded-xl border border-slate-200 bg-white px-3 py-2.5 text-sm focus:border-teal-500 outline-none';

const AdminDashboard = () => {
  const { session, nav, openPhoto } = useApp(); const list = useAdminData();
  const [q, setQ] = useState(''); const [cat, setCat] = useState('ALL'); const [st, setSt] = useState('ALL'); const [view, setView] = useState('ALL');
  let stats = { total: 0, new: 0, progress: 0, resolved: 0, pending: 0, delayed: 0 }; try { stats = api.adminStats(session.token); } catch (e) {}
  const rows = list.filter(c => (cat === 'ALL' || c.category === cat) && (st === 'ALL' || c.status === st)
    && (view === 'ALL' || (view === 'PENDING' ? c.status !== 'RESOLVED' : api.isDelayed(c)))
    && (!q.trim() || c.id.toLowerCase().includes(q.trim().toLowerCase()) || c.regNo.toLowerCase().includes(q.trim().toLowerCase())));
  return html`<${AdminShell} current="/admin">
    <${PageHead} title="Admin Dashboard" sub=${'Signed in as ' + session.user.name + '. Review complaints, assign teams and update progress.'} />
    <div class="grid grid-cols-2 lg:grid-cols-3 xl:grid-cols-5 gap-4">
      <${Stat} label="Total reports" value=${stats.total} icon="note" tone="navy" />
      <${Stat} label="New reports" value=${stats.new} icon="inbox" tone="teal" hint="Not yet reviewed" />
      <${Stat} label="In progress" value=${stats.progress} icon="wrench" tone="amber" />
      <${Stat} label="Resolved" value=${stats.resolved} icon="check" tone="green" />
      <${Stat} label="Pending" value=${stats.pending} icon="clock" tone="red" hint=${stats.delayed + ' delayed over ' + DELAY_DAYS + ' days'} />
    </div>
    <section class="bg-white rounded-2xl shadow-soft ring-1 ring-slate-100 mt-8">
      <div class="p-4 sm:p-5 border-b border-slate-100 flex flex-wrap gap-3 items-center">
        <div class="relative flex-1 min-w-[220px]"><span class="absolute left-3 top-1/2 -translate-y-1/2 text-slate-400"><${Icon} n="search" c="w-4 h-4" /></span>
          <label class="sr-only" for="adm-q">Search</label><input id="adm-q" value=${q} onInput=${e => setQ(e.target.value)} placeholder="Search by complaint ID or register number" class=${sel + ' w-full pl-9'} /></div>
        <label class="sr-only" for="adm-cat">Category</label><select id="adm-cat" value=${cat} onChange=${e => setCat(e.target.value)} class=${sel}><option value="ALL">All categories</option>${CATS.map(c => html`<option key=${c}>${c}</option>`)}</select>
        <label class="sr-only" for="adm-st">Status</label><select id="adm-st" value=${st} onChange=${e => setSt(e.target.value)} class=${sel}><option value="ALL">All statuses</option>${STATUSES.map(s => html`<option key=${s}>${s}</option>`)}</select>
        <div class="flex rounded-xl bg-slate-100 p-1 text-sm">${[['ALL', 'All'], ['PENDING', 'Pending'], ['DELAYED', 'Delayed']].map(([k, l]) => html`<button key=${k} onClick=${() => setView(k)} class=${'rounded-lg px-3 py-1.5 font-medium transition ' + (view === k ? 'bg-white shadow-soft text-navy-900' : 'text-slate-500')}>${l}</button>`)}</div>
      </div>
      <div class="tbl-wrap"><table class="w-full text-sm min-w-[980px]">
        <thead><tr class="text-left text-[11px] uppercase tracking-wider text-slate-400">${['Complaint ID', 'Student', 'Register No.', 'Category', 'Location', 'Photo', 'Submitted', 'Status', 'Action'].map(h => html`<th key=${h} class="font-semibold px-4 py-3 whitespace-nowrap">${h}</th>`)}</tr></thead>
        <tbody class="divide-y divide-slate-100">${rows.map(c => html`
          <tr key=${c.id} class="hover:bg-slate-50/70">
            <td class="px-4 py-3.5 font-semibold tabular-nums whitespace-nowrap">${c.id}</td>
            <td class="px-4 py-3.5 whitespace-nowrap">${c.studentName}</td>
            <td class="px-4 py-3.5 tabular-nums text-slate-500 whitespace-nowrap">${c.regNo}</td>
            <td class="px-4 py-3.5"><div class="flex items-center gap-2 whitespace-nowrap"><span class="text-teal-600"><${Icon} n=${CAT_ICON[c.category]} c="w-4 h-4" /></span>${c.category}</div></td>
            <td class="px-4 py-3.5 text-slate-500 min-w-[180px]">${c.building}<div class="text-xs text-slate-400">${c.floor}, ${c.room}</div></td>
            <td class="px-4 py-3.5"><${Thumb} src=${c.photo} onOpen=${openPhoto} size="w-10 h-10" /></td>
            <td class="px-4 py-3.5 whitespace-nowrap text-slate-500">${fmtDate(c.submittedAt)}</td>
            <td class="px-4 py-3.5"><div class="flex flex-col items-start gap-1.5"><${Badge} s=${c.status} />${api.isDelayed(c) ? html`<${Delayed} />` : null}</div></td>
            <td class="px-4 py-3.5"><${Btn} kind="ghost" class="!py-1.5 !px-3" onClick=${() => nav('/admin/complaints/' + c.id)}>Open<//></td>
          </tr>`)}</tbody></table>
        ${rows.length ? null : html`<div class="p-10 text-center text-slate-500">No complaints match these filters.</div>`}
      </div>
      <div class="px-5 py-3 border-t border-slate-100 text-xs text-slate-400">Showing ${rows.length} of ${list.length} complaints</div>
    </section><//>`;
};

const AdminDetail = ({ id }) => {
  useDB(); const { session, nav, openPhoto, flash } = useApp(); let c, bad = '';
  try { c = api.adminGet(session.token, id); } catch (e) { bad = e.message; }
  const [status, setStatus] = useState(c ? c.status : 'NEW'); const [team, setTeam] = useState(c ? c.team || '' : ''); const [note, setNote] = useState(''); const [busy, setBusy] = useState(false);
  useEffect(() => { if (c) { setStatus(c.status); setTeam(c.team || ''); } }, [c && c.status, c && c.team]);
  if (bad) return html`<${AdminShell} current="/admin"><div class="bg-white rounded-2xl shadow-soft p-10 text-center"><h1 class="font-serif text-2xl font-semibold">${bad}</h1><${Btn} class="mt-5" onClick=${() => nav('/admin')}>Back to dashboard<//></div><//>`;
  const dirty = status !== c.status || (team || null) !== (c.team || null);
  const save = async () => { setBusy(true); try { await api.adminUpdate(session.token, id, { status, team: team || null }); flash('Progress updated. The student can see it now.'); } catch (x) { flash(x.message, true); } setBusy(false); };
  const addNote = async () => { if (!note.trim()) return; setBusy(true); try { await api.adminUpdate(session.token, id, { note }); setNote(''); flash('Internal note saved.'); } catch (x) { flash(x.message, true); } setBusy(false); };
  const dl = (k, v) => html`<div><dt class="text-slate-400 text-xs uppercase tracking-wider">${k}</dt><dd class="font-semibold mt-0.5">${v}</dd></div>`;
  return html`<${AdminShell} current="/admin">
    <button onClick=${() => nav('/admin')} class="text-sm text-slate-500 hover:text-navy-900 inline-flex items-center gap-1.5 mb-4"><${Icon} n="left" c="w-4 h-4" />All complaints</button>
    <${PageHead} title=${c.category} sub=${'Complaint ' + c.id + ' · submitted ' + ago(c.submittedAt)} right=${html`<div class="flex items-center gap-2"><${Badge} s=${c.status} />${api.isDelayed(c) ? html`<${Delayed} />` : null}</div>`} />
    <div class="grid xl:grid-cols-[1.15fr_.85fr] gap-6 items-start">
      <div class="space-y-6 min-w-0">
        <section class="bg-white rounded-2xl shadow-soft ring-1 ring-slate-100 p-5 sm:p-6">
          <h2 class="font-semibold mb-4">Complaint details</h2>
          ${c.photo ? html`<button onClick=${() => openPhoto(c.photo)} class="block w-full relative group"><img src=${c.photo} alt="Original uploaded photo" class="w-full max-h-96 object-cover rounded-xl ring-1 ring-slate-200" /><span class="absolute right-3 bottom-3 rounded-lg bg-navy-900/80 text-white text-xs px-2.5 py-1.5 inline-flex items-center gap-1.5"><${Icon} n="eye" c="w-3.5 h-3.5" />View original</span></button>` : html`<div class="rounded-xl bg-slate-50 p-6 text-center text-sm text-slate-400">No photo uploaded</div>`}
          <dl class="grid sm:grid-cols-2 gap-x-6 gap-y-4 mt-5 text-sm">${dl('Complaint ID', c.id)}${dl('Submitted', fmtDT(c.submittedAt))}${dl('Building', c.building)}${dl('Floor / facility', c.floor + ', ' + c.room)}${dl('Problem date', fmtDate(c.problemDate))}${dl('Assigned team', teamName(c.team) || 'Unassigned')}
            <div class="sm:col-span-2"><dt class="text-slate-400 text-xs uppercase tracking-wider">Description</dt><dd class="mt-0.5 leading-relaxed">${c.description}</dd></div></dl>
        </section>
        <section class="bg-white rounded-2xl shadow-soft ring-1 ring-slate-100 p-5 sm:p-6">
          <h2 class="font-semibold mb-4">Student information</h2>
          <div class="flex items-center gap-4"><div class="w-12 h-12 rounded-full bg-navy-900 text-white grid place-items-center font-semibold">${c.student.name.split(' ').map(w => w[0]).slice(0, 2).join('')}</div>
            <div class="min-w-0 text-sm"><div class="font-semibold">${c.student.name}</div><div class="text-slate-500 tabular-nums">${c.student.regNo}</div><div class="text-slate-500 truncate">${c.student.email}</div></div></div>
        </section>
      </div>
      <div class="space-y-6 min-w-0">
        <section class="bg-white rounded-2xl shadow-soft ring-1 ring-slate-100 p-5 sm:p-6">
          <h2 class="font-semibold mb-4">Manage progress</h2>
          <label for="m-status" class="text-sm font-medium">Status</label><select id="m-status" value=${status} onChange=${e => setStatus(e.target.value)} class=${sel + ' w-full mt-1.5'}>${STATUSES.map(s => html`<option key=${s}>${s}</option>`)}</select>
          <label for="m-team" class="text-sm font-medium block mt-4">Assign maintenance team</label><select id="m-team" value=${team} onChange=${e => setTeam(e.target.value)} class=${sel + ' w-full mt-1.5'}><option value="">Unassigned</option>${TEAMS.map(t => html`<option key=${t.id} value=${t.id}>${t.name}</option>`)}</select>
          <${Btn} class="w-full mt-5" disabled=${!dirty || busy} onClick=${save}>${busy ? 'Saving…' : 'Update progress'}<//>
          ${c.status !== 'RESOLVED' ? html`<${Btn} kind="teal" class="w-full mt-2.5" disabled=${busy} onClick=${async () => { setBusy(true); try { await api.adminUpdate(session.token, id, { status: 'RESOLVED', team: team || null }); flash('Marked as resolved.'); } catch (x) { flash(x.message, true); } setBusy(false); }}><${Icon} n="check" c="w-4 h-4" />Mark as resolved<//>` : null}
          <p class="text-xs text-slate-400 mt-3">Each change is timestamped in the history and shown to the student immediately.</p>
        </section>
        <section class="bg-white rounded-2xl shadow-soft ring-1 ring-slate-100 p-5 sm:p-6">
          <h2 class="font-semibold">Internal notes</h2><p class="text-xs text-slate-400 mt-0.5">Visible to administrators only.</p>
          <div class="mt-4 space-y-3">${c.internalNotes.length ? c.internalNotes.map((n, i) => html`<div key=${i} class="rounded-xl bg-navy-50 p-3.5 text-sm"><div>${n.text}</div><div class="text-xs text-slate-400 mt-1.5">${n.by} · ${fmtDT(n.at)}</div></div>`) : html`<p class="text-sm text-slate-400">No notes yet.</p>`}</div>
          <label for="m-note" class="sr-only">Add note</label><textarea id="m-note" rows="3" value=${note} onInput=${e => setNote(e.target.value)} placeholder="Add an internal note" class=${sel + ' w-full mt-4'}></textarea>
          <${Btn} kind="ghost" class="mt-2.5" disabled=${!note.trim() || busy} onClick=${addNote}>Add note<//>
        </section>
        <section class="bg-white rounded-2xl shadow-soft ring-1 ring-slate-100 p-5 sm:p-6"><h2 class="font-semibold mb-5">Complaint history</h2><${Timeline} items=${[...c.history].reverse()} /></section>
      </div>
    </div><//>`;
};

const Maintenance = () => {
  const list = useAdminData(); const { session, nav, flash } = useApp();
  const open = list.filter(c => c.status !== 'RESOLVED'); const unassigned = open.filter(c => !c.team);
  const assign = async (id, team) => { try { await api.adminUpdate(session.token, id, { team: team || null }); flash(team ? 'Assigned to ' + teamName(team) + '.' : 'Assignment removed.'); } catch (x) { flash(x.message, true); } };
  const Row = ({ c }) => html`<div class="flex flex-wrap items-center gap-3 py-3 border-t border-slate-100 first:border-t-0">
    <div class="min-w-0 flex-1 basis-48"><button onClick=${() => nav('/admin/complaints/' + c.id)} class="font-semibold text-sm text-navy-700 hover:text-teal-600 tabular-nums">${c.id}</button><div class="text-sm text-slate-500 truncate">${c.category} · ${c.building}</div></div>
    ${api.isDelayed(c) ? html`<${Delayed} />` : null}<${Badge} s=${c.status} />
    <label class="sr-only" for=${'as-' + c.id}>Team</label><select id=${'as-' + c.id} value=${c.team || ''} onChange=${e => assign(c.id, e.target.value)} class=${sel + ' !py-1.5'}><option value="">Unassigned</option>${TEAMS.map(t => html`<option key=${t.id} value=${t.id}>${t.name}</option>`)}</select></div>`;
  return html`<${AdminShell} current="/admin/maintenance">
    <${PageHead} title="Maintenance Assignments" sub="Balance the workload across teams and assign any complaint that is still waiting." />
    <div class="grid md:grid-cols-3 gap-4">${TEAMS.map(t => { const mine = list.filter(c => c.team === t.id); const act = mine.filter(c => c.status !== 'RESOLVED').length;
      return html`<div key=${t.id} class="bg-white rounded-2xl shadow-soft ring-1 ring-slate-100 p-5">
        <div class="flex items-center gap-3"><span class="w-10 h-10 rounded-xl bg-teal-100 text-teal-700 grid place-items-center"><${Icon} n="users" /></span><div class="min-w-0"><div class="font-semibold leading-tight">${t.name}</div><div class="text-xs text-slate-400">Lead: ${t.lead} · ${t.phone}</div></div></div>
        <div class="grid grid-cols-2 gap-3 mt-5"><div class="rounded-xl bg-amber-50 p-3"><div class="font-serif text-2xl font-semibold tabular-nums">${act}</div><div class="text-xs text-slate-500">Active jobs</div></div><div class="rounded-xl bg-emerald-50 p-3"><div class="font-serif text-2xl font-semibold tabular-nums">${mine.length - act}</div><div class="text-xs text-slate-500">Completed</div></div></div></div>`; })}</div>
    <section class="bg-white rounded-2xl shadow-soft ring-1 ring-slate-100 p-5 sm:p-6 mt-6">
      <div class="flex items-center justify-between"><h2 class="font-semibold">Waiting for assignment</h2><span class="text-sm text-slate-400">${unassigned.length} open</span></div>
      <div class="mt-2">${unassigned.length ? unassigned.map(c => html`<${Row} key=${c.id} c=${c} />`) : html`<p class="text-sm text-slate-500 py-6 text-center">Every open complaint has a team.</p>`}</div></section>
    <section class="bg-white rounded-2xl shadow-soft ring-1 ring-slate-100 p-5 sm:p-6 mt-6">
      <h2 class="font-semibold">Assigned and open</h2>
      <div class="mt-2">${open.filter(c => c.team).length ? open.filter(c => c.team).map(c => html`<${Row} key=${c.id} c=${c} />`) : html`<p class="text-sm text-slate-500 py-6 text-center">No assigned jobs are open.</p>`}</div></section><//>`;
};

/* ================= APP + ROUTE PROTECTION ================= */
const App = () => {
  const [ready, setReady] = useState(false);
  const [session, setSession] = useState(null);
  const [path, setPath] = useState('/');
  const [toast, setToast] = useState(null);
  const [photo, setPhotoSrc] = useState(null);
  useEffect(() => { seed().then(() => { setReady(true); try { bc && bc.postMessage({ t: 'hello' }); } catch (e) {} }); }, []);
  useEffect(() => { window.scrollTo(0, 0); }, [path]);
  const flash = (msg, err) => { setToast({ msg, err }); clearTimeout(flash.t); flash.t = setTimeout(() => setToast(null), 3200); };
  const nav = (p) => setPath(p.startsWith('/') ? p : '/' + p);
  const home = (u) => u.role === 'ADMIN' ? '/admin' : '/student';
  const signIn = async (role, id, pw) => { const r = await api.login(role, id, pw); setSession(r); setPath(home(r.user)); flash('Welcome, ' + r.user.name.split(' ')[0] + '.'); };
  const logout = () => { if (session) api.logout(session.token); setSession(null); setPath('/'); };
  const ctx = { session, path, nav, flash, signIn, logout, openPhoto: setPhotoSrc };

  /* Route guard. The role comes from the server-issued session; the API layer re-checks it on every call. */
  const resolve = () => {
    const role = session && session.user.role;
    if (path === '/') return html`<${Landing} />`;
    if (path === '/student/login' || path === '/admin/login') {
      const want = path === '/admin/login' ? 'ADMIN' : 'STUDENT';
      if (!session) return html`<${LoginPage} role=${want} />`;
      if (role === want) return resolveProtected(home(session.user));
      return html`<${Denied} reason=${'You are signed in as ' + (role === 'ADMIN' ? 'an administrator' : 'a student') + '. Sign out first to use the ' + (want === 'ADMIN' ? 'Admin' : 'Student') + ' Portal login.'} />`;
    }
    return resolveProtected(path);
  };
  const resolveProtected = (p) => {
    const role = session && session.user.role;
    const isAdminRoute = p === '/admin' || p.startsWith('/admin/'); const isStudentRoute = p === '/student' || p.startsWith('/student/');
    if (!isAdminRoute && !isStudentRoute) return html`<${Denied} reason="This page does not exist." />`;
    if (!session) return html`<${LoginPage} role=${isAdminRoute ? 'ADMIN' : 'STUDENT'} />`;
    if (isAdminRoute && role !== 'ADMIN') return html`<${Denied} reason="This area is restricted to administrators. Your student account cannot open admin pages." />`;
    if (isStudentRoute && role !== 'STUDENT') return html`<${Denied} reason="This area is for students. Administrators manage complaints from the Admin Portal." />`;
    const id = p.split('/')[3];
    if (p === '/student') return html`<${StudentDashboard} />`;
    if (p === '/student/report') return html`<${ReportForm} />`;
    if (p === '/student/complaints') return html`<${MyComplaints} />`;
    if (p.startsWith('/student/complaints/') && id) return html`<${StudentDetail} id=${id} key=${id} />`;
    if (p === '/admin') return html`<${AdminDashboard} />`;
    if (p === '/admin/maintenance') return html`<${Maintenance} />`;
    if (p.startsWith('/admin/complaints/') && id) return html`<${AdminDetail} id=${id} key=${id} />`;
    return html`<${Denied} reason="This page does not exist." />`;
  };
  if (!ready) return html`<div class="min-h-screen grid place-items-center"><${Logo} /></div>`;
  return html`<${Ctx.Provider} value=${ctx}>${resolve()}<${DemoDock} /><${Toast} t=${toast} /><${Lightbox} src=${photo} onClose=${() => setPhotoSrc(null)} /><//>`;
};
ReactDOM.createRoot(document.getElementById('root')).render(html`<${App} />`);
</script>

</body></html>
