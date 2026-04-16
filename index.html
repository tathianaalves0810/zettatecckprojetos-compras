import { useState, useMemo, useEffect, useCallback } from 'react';

// ─── SUPABASE CONFIG ──────────────────────────────────────────────────────────
const SUPA_URL = 'https://hgfewmytnjvlcomtjygk.supabase.co';
const SUPA_KEY =
  'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImhnZmV3bXl0bmp2bGNvbXRqeWdrIiwicm9sZSI6ImFub24iLCJpYXQiOjE3NzYwMzU3MDQsImV4cCI6MjA5MTYxMTcwNH0.0dWTlfperPeMIIKxvwCQD7UahokzGCjbwTQfBAcIz_c';
const H = {
  'Content-Type': 'application/json',
  apikey: SUPA_KEY,
  Authorization: `Bearer ${SUPA_KEY}`,
  Prefer: 'return=representation',
};

async function sbGet(table, query = '') {
  const r = await fetch(`${SUPA_URL}/rest/v1/${table}?${query}`, {
    headers: H,
  });
  if (!r.ok) throw new Error(await r.text());
  return r.json();
}
async function sbInsert(table, body) {
  const r = await fetch(`${SUPA_URL}/rest/v1/${table}`, {
    method: 'POST',
    headers: H,
    body: JSON.stringify(body),
  });
  if (!r.ok) throw new Error(await r.text());
  return r.json();
}
async function sbUpdate(table, id, body) {
  const r = await fetch(`${SUPA_URL}/rest/v1/${table}?id=eq.${id}`, {
    method: 'PATCH',
    headers: H,
    body: JSON.stringify(body),
  });
  if (!r.ok) throw new Error(await r.text());
  return r.json();
}
async function sbDelete(table, id) {
  const r = await fetch(`${SUPA_URL}/rest/v1/${table}?id=eq.${id}`, {
    method: 'DELETE',
    headers: H,
  });
  if (!r.ok) throw new Error(await r.text());
}

// ─── LOGO ─────────────────────────────────────────────────────────────────────
const LOGO =
  'data:image/png;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/4gHYSUNDX1BST0ZJTEUAAQEAAAHIAAAAAAQwAABtbnRyUkdCIFhZWiAH4AABAAEAAAAAAABhY3NwAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQAA9tYAAQAAAADTLQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAlkZXNjAAAA8AAAACRyWFlaAAABFAAAABRnWFlaAAABKAAAABRiWFlaAAABPAAAABR3dHB0AAABUAAAABRyVFJDAAABZAAAAChnVFJDAAABZAAAAChiVFJDAAABZAAAAChjcHJ0AAABjAAAADxtbHVjAAAAAAAAAAEAAAAMZW5VUwAAAAgAAAAcAHMAUgBHAEJYWVogAAAAAAAAb6IAADj1AAADkFhZWiAAAAAAAABimQAAt4UAABjaWFlaIAAAAAAAACSgAAAPhAAAts9YWVogAAAAAAAA9tYAAQAAAADTLXBhcmEAAAAAAAQAAAACZmYAAPKnAAANWQAAE9AAAApbAAAAAAAAAABtbHVjAAAAAAAAAAEAAAAMZW5VUwAAACAAAAAcAEcAbwBvAGcAbABlACAASQBuAGMALgAgADIAMAAxADb/2wBDAAUDBAQEAwUEBAQFBQUGBwwIBwcHBw8LCwkMEQ8SEhEPERETFhwXExQaFRERGCEYGh0dHx8fExciJCIeJBweHx7/2wBDAQUFBQcGBw4ICA4eFBEUHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh7/wAARCACRAJcDASIAAhEBAxEB/8QAHAABAQACAwEBAAAAAAAAAAAAAAECBwMFBggE/8QAPxAAAQMDAQcCAQcICwAAAAAAAAECAwQFEQYHEiExMnGRE1JRCBQWIkFhsRUXN1aBwcLRMzQ2QkNic3R1oaL/xAAbAQEBAAMBAQEAAAAAAAAAAAAAAQMEBQYCCP/EAC4RAAIBAwMCBAUEAwAAAAAAAAABAgMEEQUSITFBExQiUQZhgZGhFRZx0SMy4f/aAAwDAQACEQMRAD8Aza1u6n1U5fAu632p4DelOxT3p+bybrfangbrfangoAJut9qeBut9qeCgAm632p4G632p4KACbrfangbrfangoAJut9qeBut9qeCgAm632p4G632p4KACbrfangbrfangoAJut9qeBut9qeCgAwka3d6U8AsnSCohW9Kdikb0p2KQoAAAAAAAAAAAAAAAAAAAAAAABjJ0gSdIKiMrelOxSN6U7FIUAAAAAAAAAAAAAAAAAAAAAAAAxk6QJOkFRGVvSnYpG9KdikKAAAAAAAAAAAAAAAAAAAAAAAAYydIEnSCojK3pTsUjelOxSFAAAAAAAAAAAAAAAAAAAAAAAAMZOkCTpBURlb0p2KRvSnYpCgAAAAAAAAAAAAAAAAAAAAAAAGMnSBJ0gqIyt6U7FI3pTsUhQAAAAAAAAAAAAAAAAAAAAAAADGTpAk6QVEZW9Kdj32jdB2m/WWGuqdU09BPI9W/N3I1XJheHNyLxPAt6U7Hs9jtgS+a0p3Sxo6no09eXKcFVOlPODVu240nJSxg6ujQhVu40p0vE3cYba+vHsekvWyGK3RU7/wAvvk9adsOFp0TGft6jmrNkNrontZWaxip3O4tSWJrVXy49DtHvO9r3TNhifwbUJUTJ5Rv7zk2r6OptS3CjnnvlHblijVqNmVMuyvNMqcaF3X9HiTwmm+i/o93W0bTv8/l7dTcGljc1zjL5z8zxOmdmVtvcciR6qiSZkr2JEyNrnK1q43sb2cKcl+2XW20yU0c2q4kkmnZE5r42tVjXZ+vje5Ifl2IU7aXahPTNe2RIYJ40e3k7DkTKdzH5QaJ9N2LhP6o38VNvfXd14SqcYz0RxvA0+OkO8dutylt/2l9+p3rdjVC6l+dN1Wi0+7veqkDdzHxzvYweIfpSF+votMUV0ZVQyPanztjUVMKmVXCLjh3Nt2hE/MY9MJj8mycP2Ka52B0fzjXkc+7ltNA9691TCHxQuK2yrOc87crojPqGmWLr2lCjR2+LtbeW+O65f56n79Z7Kfo/pyqu8V4fVOp0RfSWBG5RVRF45X4n5NDbO6DU1ohq11JHT1Mmc0yRtc9qJ928i/8ARtu6SpfNK6jpF+s6J9RAifBWpwNPbCG42gRIqJvJC9F8HzRua87ebcvVH5L2Mt9pWn2+p28IUs06ixjL4eevXP0O2u+ymgoKiCm+lLH1M0rWJCsLUfhftxvZP2Vmx23USNWs1cynRy4assLW57ZcZa1RPz+2lcf4cX8R6/axpeDU1JQxT3emtyQyOcjplTDsonLKmN3VaLpqVTCksvhG1DSLCpG5dO2TdOW1LdJZ6d8mr9GbNpdQVddI64thtlJO6FtQ1qKsyt+1EzhExjiTXWzl9jtUd3tVxbcqFz0Y5URMtVVwmMKqKmTZOyaBtNs7qqdr2yJFLUM328nYymU74NaWbXcjdM0uj1t0bo/VRnrrJx4yZzjH3meFe4qVpbHlRaWPl7nOuNO0u2sqSrRxOpFtSy3iXGFjpjnv7HeWrY+xbfTyXm+JR1dRhGQtYi4Vf7vFeKnXWrZXVVGqq6x11y+bpTwNnimZFvJK1VxyVUwe3233J1nTTt1bEkrqSvWVGKuEdhvLJhsx1dJrDV9ZWSUTKRaegbFutfvb2ZM5MEbm7dF1s8fTjk6FTSdGjfRsXDE013fqTjl57L8Hj6PZWk+pbpa33l0dNb4o3uqfQT6yuTOMZ4YT7zXFUxkdTLHE9ZGMerWuVMbyIvM+ldoarZ9IX65UrHOqKmJGvVOaJjdz+xFPmVOXxN7Tq9SunOT44X45PP8AxRp1tp04UaMcSe5vl9G/SufZEk6QJOkHTR5Nlb0p2PoPYNZW27SC3J6J61e/1M/5E4N/efPjelOx31u1hqi3UcdFQ3uqgp4kwyNqphqeDSvredxT2QeDvfD2p2+m3XmK0XLCaWMdX/PyPXy0d/q9q8F8uFsqoKV9cjWPkbwa1OCId3t5sN3u92t0ltt09UxkTkcsbc4XJrep1pqupaxtRfauRGPR7UVU4OTkvI5fp7rL9Yqzyn8jB5WupwmselY7nQ/V9Plb1ree9qpJSb9Oc/c9DsMp56TaU6mqYnRTR0kqPY5OLVy0x+UF/bdn+0b+KnjqW/Xmlu8l3p7jNHXyoqPnTG87PP8AA4bxdbjeKpKq6VklXOjd3ffzx8DMrafmVWb7YNGWq0VpTsYp537k+On9m+LR+g5//Gyfgp5r5NtGqzXa4Y4I1kOf/RriPVOoo7Utqju1Q2hVix+gmN3dXmnIwsuo77ZIJILTc56OOR289sePrLjGeRruwqeFUgmvU8nTXxHbO7tq8oPFKOH05eMccn0NoW52661OoIaO3NpUhrnMmVHq713KnF6/DPwNW7JKV1FtZqKR6YWJZm/ieMtWpb/anzvt11qKZ1Q/fmVip9d3xXgcVNfLvTXeS709fNHXyKqvnTG85V5iFhOCqJPiSwSv8SUa7tpzg91KTbwkk03nj8Gz9a/p8tP+nF/Edzt7s9zu9vtrLbQy1bo5XK5I0zjghpiqv14qrvHd6i4TSV8aIjJ1xvNxy/E7L6e6y/WKs8p/IeSqxlTlFrMVjuX9wWdSldUasZYqy3cYylx7v5G3tjLX/QKqtj2Kyrp5ZYpIncHNcqcMnWVVqpNN7KKdbvQU8FybIjVcrWq/eWTKcexqag1JfaG5zXKkulRFVzrmWRF/pO6clML9f7zfpGyXa4TVSs6EcuGt7InAnkKjquW7htN+/wDBf3JbKzjTVNucYuCzjGHjl988I+hNb2ma/VumZ6aBlXRw1yTVCqqK301bz480OS1xW2n2i1NLboYIVitjfWbE1Ew5ZMpnH3Gg7VrPVFroUoqG81EUCJhrOC7vbKcD8lu1FfLdXT11FdKiGpqExNKjsufxzxyYVpdXa4blhLj79zel8XWfiqsqT3Npy6cYWMR/6fRs8jb1Uak07KqfUia1qL8JGKufJ8w1ELqeolgeio6N6sVF+5cHbw6s1LDcZrjFeallXO1GSyoqZeickXgdTVTzVVTJU1EiySyOVz3rzcq/abtlaStm03w8ffucLX9ao6ooOMWpRcuuOjeV9jhk6QJOkHQR5plb0p2KAQoAAAAAAAAAAAAAAAAAAAAAAABjJ0gAqIz/2Q==';

// inject global reset
if (typeof document !== 'undefined') {
  const s = document.createElement('style');
  s.textContent = `*,*::before,*::after{box-sizing:border-box;margin:0;padding:0;}body,html{width:100%;height:100%;overflow-x:hidden;}#root{min-height:100vh;}`;
  document.head.appendChild(s);
}

// ─── UTILS ────────────────────────────────────────────────────────────────────
const fmt = (v) =>
  new Intl.NumberFormat('pt-BR', { style: 'currency', currency: 'BRL' }).format(
    v || 0
  );
const fmtDate = (d) => {
  if (!d) return '—';
  const [y, m, dd] = d.split('-');
  return `${dd}/${m}/${y}`;
};
// Parseia data YYYY-MM-DD como data LOCAL (evita problema de fuso UTC)
const parseLocal = (d) => {
  if (!d) return null;
  const [y, m, dd] = d.split('-');
  return new Date(parseInt(y), parseInt(m) - 1, parseInt(dd));
};
const uid = () => Date.now().toString(36) + Math.random().toString(36).slice(2);

const SC = {
  Concluído: { bg: '#D1FAE5', text: '#065F46', dot: '#10B981' },
  Aguardando: { bg: '#FEF3C7', text: '#92400E', dot: '#F59E0B' },
  'Faturado Inicial': { bg: '#DBEAFE', text: '#1E40AF', dot: '#3B82F6' },
  'Entregue Parcial': { bg: '#EDE9FE', text: '#5B21B6', dot: '#8B5CF6' },
  ENTREGUE: { bg: '#D1FAE5', text: '#065F46', dot: '#10B981' },
  'NÃO ENTREGUE': { bg: '#FEE2E2', text: '#991B1B', dot: '#EF4444' },
  'Pago total': { bg: '#D1FAE5', text: '#065F46', dot: '#10B981' },
  'Pago parcial': { bg: '#FEF3C7', text: '#92400E', dot: '#F59E0B' },
  'Não pago': { bg: '#FEE2E2', text: '#991B1B', dot: '#EF4444' },
  ativo: { bg: '#D1FAE5', text: '#065F46', dot: '#10B981' },
  pendente: { bg: '#FEF3C7', text: '#92400E', dot: '#F59E0B' },
  rejeitado: { bg: '#FEE2E2', text: '#991B1B', dot: '#EF4444' },
  'ENTREGUE PARCIAL': { bg: '#FEF3C7', text: '#92400E', dot: '#F59E0B' },
  'SEM ENTREGA': { bg: '#D1FAE5', text: '#065F46', dot: '#10B981' },
};

// formata nome: Primeira letra de cada palavra maiúscula, resto minúsculo
// exige pelo menos nome e sobrenome
function formatarNome(str) {
  if (!str) return '';
  return str
    .trim()
    .split(/\s+/)
    .map((p) => p.charAt(0).toUpperCase() + p.slice(1).toLowerCase())
    .join(' ');
}
function validarNome(str) {
  const partes = str.trim().split(/\s+/).filter(Boolean);
  return partes.length >= 2;
}

function Badge({ s }) {
  const c = SC[s] || { bg: '#F3F4F6', text: '#374151', dot: '#9CA3AF' };
  return (
    <span
      style={{
        display: 'inline-flex',
        alignItems: 'center',
        gap: 5,
        padding: '3px 10px',
        borderRadius: 20,
        background: c.bg,
        color: c.text,
        fontSize: 12,
        fontWeight: 600,
        whiteSpace: 'nowrap',
      }}
    >
      <span
        style={{ width: 6, height: 6, borderRadius: '50%', background: c.dot }}
      />
      {s}
    </span>
  );
}
function Spin() {
  return (
    <div
      style={{
        display: 'flex',
        alignItems: 'center',
        justifyContent: 'center',
        padding: 60,
        color: '#94A3B8',
        fontSize: 14,
        gap: 10,
      }}
    >
      <div
        style={{
          width: 20,
          height: 20,
          border: '3px solid #E2E8F0',
          borderTop: '3px solid #00BCD4',
          borderRadius: '50%',
          animation: 'spin 0.8s linear infinite',
        }}
      />
      <style>{`@keyframes spin{to{transform:rotate(360deg)}}`}</style>
      Carregando...
    </div>
  );
}

const INP = {
  width: '100%',
  padding: '10px 14px',
  border: '1.5px solid #E2E8F0',
  borderRadius: 9,
  fontSize: 13,
  fontFamily: 'inherit',
  outline: 'none',
  boxSizing: 'border-box',
  color: '#1E293B',
  background: '#FAFAFA',
};
const INP_DK = {
  width: '100%',
  padding: '12px 16px',
  border: '1.5px solid #1E293B',
  borderRadius: 10,
  fontSize: 14,
  fontFamily: 'inherit',
  outline: 'none',
  boxSizing: 'border-box',
  color: '#F1F5F9',
  background: '#1E293B',
};
const LBL = {
  fontSize: 11,
  fontWeight: 700,
  color: '#64748B',
  textTransform: 'uppercase',
  letterSpacing: 0.6,
  display: 'block',
  marginBottom: 5,
};
const SAVE_BTN = {
  padding: '9px 24px',
  border: 'none',
  borderRadius: 9,
  background: '#00BCD4',
  color: '#fff',
  fontWeight: 800,
  cursor: 'pointer',
  fontFamily: 'inherit',
};
const CANCEL_BTN = {
  padding: '9px 20px',
  border: '1.5px solid #E2E8F0',
  borderRadius: 9,
  background: 'none',
  color: '#64748B',
  fontWeight: 600,
  cursor: 'pointer',
  fontFamily: 'inherit',
};

function Modal({ title, onClose, children, wide }) {
  return (
    <div
      style={{
        position: 'fixed',
        inset: 0,
        background: 'rgba(15,23,42,0.65)',
        display: 'flex',
        alignItems: 'center',
        justifyContent: 'center',
        zIndex: 1000,
        backdropFilter: 'blur(4px)',
      }}
    >
      <div
        style={{
          background: '#fff',
          borderRadius: 16,
          width: '90%',
          maxWidth: wide ? 700 : 520,
          maxHeight: '90vh',
          overflowY: 'auto',
          boxShadow: '0 25px 60px rgba(0,0,0,.25)',
        }}
      >
        <div
          style={{
            padding: '20px 24px',
            borderBottom: '1px solid #F1F5F9',
            display: 'flex',
            justifyContent: 'space-between',
            alignItems: 'center',
          }}
        >
          <div style={{ fontSize: 16, fontWeight: 800, color: '#0F172A' }}>
            {title}
          </div>
          <button
            onClick={onClose}
            style={{
              background: 'none',
              border: 'none',
              fontSize: 20,
              color: '#94A3B8',
              cursor: 'pointer',
            }}
          >
            ✕
          </button>
        </div>
        <div style={{ padding: '20px 24px' }}>{children}</div>
      </div>
    </div>
  );
}
function Btn({ icon, bg, color, onClick, title }) {
  return (
    <button
      title={title}
      onClick={onClick}
      style={{
        width: 30,
        height: 30,
        border: 'none',
        borderRadius: 7,
        background: bg || '#F1F5F9',
        color: color || '#374151',
        fontSize: 14,
        cursor: 'pointer',
        display: 'inline-flex',
        alignItems: 'center',
        justifyContent: 'center',
      }}
    >
      {icon}
    </button>
  );
}
function KPI({ label, value, sub, color, icon }) {
  return (
    <div
      style={{
        background: '#fff',
        borderRadius: 14,
        padding: '16px 20px',
        borderLeft: `4px solid ${color}`,
        boxShadow: '0 2px 8px rgba(0,0,0,.06)',
      }}
    >
      <div style={{ fontSize: 20 }}>{icon}</div>
      <div
        style={{
          fontSize: 22,
          fontWeight: 900,
          color: '#0F172A',
          marginTop: 4,
          letterSpacing: -1,
        }}
      >
        {value}
      </div>
      <div
        style={{
          fontSize: 11,
          fontWeight: 700,
          color: '#64748B',
          textTransform: 'uppercase',
          letterSpacing: 0.5,
        }}
      >
        {label}
      </div>
      {sub && (
        <div style={{ fontSize: 11, color, fontWeight: 600, marginTop: 2 }}>
          {sub}
        </div>
      )}
    </div>
  );
}
function TH({ children }) {
  return (
    <th
      style={{
        padding: '9px 12px',
        textAlign: 'left',
        fontSize: 11,
        fontWeight: 700,
        color: '#64748B',
        textTransform: 'uppercase',
        borderBottom: '2px solid #F1F5F9',
        background: '#FAFAFA',
        whiteSpace: 'nowrap',
      }}
    >
      {children}
    </th>
  );
}
function TD({ children, style = {} }) {
  return (
    <td style={{ padding: '9px 12px', fontSize: 13, ...style }}>{children}</td>
  );
}

// ─── LOGIN ────────────────────────────────────────────────────────────────────
function Login({ onLogin }) {
  const [mode, setMode] = useState('login');
  const [email, setEmail] = useState('');
  const [senha, setSenha] = useState('');
  const [nome, setNome] = useState('');
  const [conf, setConf] = useState('');
  const [emailRecup, setEmailRecup] = useState('');
  const [novaSenha, setNovaSenha] = useState('');
  const [confNova, setConfNova] = useState('');
  const [erro, setErro] = useState('');
  const [ok, setOk] = useState('');
  const [loading, setLoading] = useState(false);

  async function doLogin(e) {
    e.preventDefault();
    setErro('');
    setLoading(true);
    try {
      const data = await sbGet(
        'usuarios',
        `email=eq.${encodeURIComponent(email)}&senha=eq.${encodeURIComponent(
          senha
        )}`
      );
      if (!data.length) {
        setErro('E-mail ou senha incorretos.');
        return;
      }
      const u = data[0];
      if (u.status === 'pendente') {
        setErro('Cadastro aguardando aprovação do administrador.');
        return;
      }
      if (u.status === 'rejeitado') {
        setErro('Cadastro rejeitado. Contate suprimentos@zettatecck.com.br');
        return;
      }
      onLogin(u);
    } catch (err) {
      setErro('Erro de conexão. Tente novamente.');
    } finally {
      setLoading(false);
    }
  }

  async function doReg(e) {
    e.preventDefault();
    setErro('');
    setOk('');
    if (!nome || !email || !senha || !conf) {
      setErro('Preencha todos os campos.');
      return;
    }
    if (!validarNome(nome)) {
      setErro('Digite nome e sobrenome. Ex: Maria Silva');
      return;
    }
    if (senha !== conf) {
      setErro('As senhas não coincidem.');
      return;
    }
    if (senha.length < 6) {
      setErro('A senha deve ter pelo menos 6 caracteres.');
      return;
    }
    const nomeFormatado = formatarNome(nome);
    setLoading(true);
    try {
      const existe = await sbGet(
        'usuarios',
        `email=eq.${encodeURIComponent(email)}`
      );
      if (existe.length) {
        setErro('E-mail já cadastrado.');
        return;
      }
      await sbInsert('usuarios', {
        id: uid(),
        nome: nomeFormatado,
        email,
        senha,
        perfil: 'Usuário',
        status: 'pendente',
      });
      setOk('Solicitação enviada! Aguarde aprovação do administrador.');
      setMode('login');
      setNome('');
      setSenha('');
      setConf('');
    } catch (err) {
      setErro('Erro ao cadastrar. Tente novamente.');
    } finally {
      setLoading(false);
    }
  }

  async function doRecuperar(e) {
    e.preventDefault();
    setErro('');
    setOk('');
    if (!emailRecup) {
      setErro('Digite seu e-mail.');
      return;
    }
    if (!novaSenha || !confNova) {
      setErro('Preencha a nova senha.');
      return;
    }
    if (novaSenha.length < 6) {
      setErro('A senha deve ter pelo menos 6 caracteres.');
      return;
    }
    if (novaSenha !== confNova) {
      setErro('As senhas não coincidem.');
      return;
    }
    setLoading(true);
    try {
      const data = await sbGet(
        'usuarios',
        `email=eq.${encodeURIComponent(emailRecup)}`
      );
      if (!data.length) {
        setErro('E-mail não encontrado no sistema.');
        return;
      }
      await sbUpdate('usuarios', data[0].id, { senha: novaSenha });
      setOk('Senha redefinida com sucesso! Faça login com a nova senha.');
      setMode('login');
      setEmailRecup('');
      setNovaSenha('');
      setConfNova('');
    } catch (err) {
      setErro('Erro ao redefinir. Tente novamente.');
    } finally {
      setLoading(false);
    }
  }

  const BIG_BTN = {
    width: '100%',
    padding: '14px',
    border: 'none',
    borderRadius: 10,
    background: loading ? '#64748B' : '#00BCD4',
    color: '#0A0F1E',
    fontSize: 15,
    fontWeight: 900,
    cursor: loading ? 'not-allowed' : 'pointer',
    fontFamily: 'inherit',
    marginTop: 4,
  };

  return (
    <div
      style={{
        minHeight: '100vh',
        display: 'flex',
        fontFamily: "'IBM Plex Sans','Segoe UI',sans-serif",
        background: '#0A0F1E',
      }}
    >
      <div
        style={{
          flex: '0 0 45%',
          background:
            'linear-gradient(160deg,#00BCD4 0%,#006064 60%,#0A0F1E 100%)',
          display: 'flex',
          flexDirection: 'column',
          alignItems: 'center',
          justifyContent: 'center',
          padding: '60px 48px',
          position: 'relative',
          overflow: 'hidden',
        }}
      >
        <div
          style={{
            position: 'absolute',
            width: 420,
            height: 420,
            borderRadius: '50%',
            border: '1px solid rgba(255,255,255,.08)',
            top: -80,
            left: -120,
          }}
        />
        <div
          style={{
            position: 'absolute',
            width: 280,
            height: 280,
            borderRadius: '50%',
            border: '1px solid rgba(255,255,255,.06)',
            bottom: 40,
            right: -80,
          }}
        />
        <div style={{ position: 'relative', zIndex: 1, textAlign: 'center' }}>
          <div
            style={{
              display: 'inline-flex',
              alignItems: 'center',
              justifyContent: 'center',
              width: 110,
              height: 110,
              borderRadius: 28,
              background: 'rgba(255,255,255,.12)',
              backdropFilter: 'blur(8px)',
              border: '1.5px solid rgba(255,255,255,.2)',
              boxShadow: '0 12px 40px rgba(0,0,0,.3)',
              marginBottom: 28,
            }}
          >
            <img
              src={LOGO}
              alt="Zettatecck"
              style={{
                width: 80,
                height: 80,
                borderRadius: 18,
                objectFit: 'cover',
              }}
            />
          </div>
          <div
            style={{
              color: '#fff',
              fontSize: 30,
              fontWeight: 900,
              letterSpacing: -1,
              lineHeight: 1.1,
              marginBottom: 10,
            }}
          >
            Zettatecck
            <br />
            Projetos
          </div>
          <div
            style={{
              color: 'rgba(255,255,255,.65)',
              fontSize: 13,
              lineHeight: 1.8,
              maxWidth: 280,
              margin: '0 auto',
            }}
          >
            Sistema de gestão de compras, pedidos, projetos e follow-up de
            pendências em tempo real.
          </div>
          <div
            style={{
              display: 'flex',
              gap: 10,
              justifyContent: 'center',
              marginTop: 32,
              flexWrap: 'wrap',
            }}
          >
            {[
              '📦 Pedidos',
              '📁 Projetos',
              '💳 Pagamentos',
              '🚨 Pendências',
            ].map((t) => (
              <span
                key={t}
                style={{
                  fontSize: 11,
                  fontWeight: 600,
                  padding: '5px 12px',
                  borderRadius: 20,
                  background: 'rgba(255,255,255,.1)',
                  color: 'rgba(255,255,255,.8)',
                  border: '1px solid rgba(255,255,255,.15)',
                }}
              >
                {t}
              </span>
            ))}
          </div>
        </div>
      </div>
      <div
        style={{
          flex: 1,
          display: 'flex',
          alignItems: 'center',
          justifyContent: 'center',
          padding: '40px 32px',
        }}
      >
        <div style={{ width: '100%', maxWidth: 400 }}>
          <div style={{ marginBottom: 28 }}>
            <div
              style={{
                color: '#fff',
                fontSize: 24,
                fontWeight: 900,
                letterSpacing: -0.5,
              }}
            >
              {mode === 'login'
                ? 'Bem-vindo de volta 👋'
                : mode === 'register'
                ? 'Criar nova conta'
                : 'Redefinir senha 🔑'}
            </div>
            <div style={{ color: '#64748B', fontSize: 14, marginTop: 6 }}>
              {mode === 'login'
                ? 'Entre com suas credenciais para acessar.'
                : mode === 'register'
                ? 'Preencha os dados para solicitar acesso.'
                : 'Informe seu e-mail e crie uma nova senha.'}
            </div>
          </div>
          {mode !== 'forgot' && (
            <div
              style={{
                display: 'flex',
                background: '#1E293B',
                borderRadius: 12,
                padding: 4,
                marginBottom: 24,
              }}
            >
              {[
                ['login', 'Entrar'],
                ['register', 'Cadastrar'],
              ].map(([m, l]) => (
                <button
                  key={m}
                  onClick={() => {
                    setMode(m);
                    setErro('');
                    setOk('');
                  }}
                  style={{
                    flex: 1,
                    padding: '9px',
                    border: 'none',
                    borderRadius: 9,
                    background: mode === m ? '#00BCD4' : 'transparent',
                    color: mode === m ? '#0A0F1E' : '#64748B',
                    fontWeight: 800,
                    fontSize: 13,
                    cursor: 'pointer',
                    fontFamily: 'inherit',
                  }}
                >
                  {l}
                </button>
              ))}
            </div>
          )}
          {erro && (
            <div
              style={{
                background: 'rgba(239,68,68,.12)',
                color: '#F87171',
                padding: '10px 14px',
                borderRadius: 10,
                fontSize: 13,
                marginBottom: 14,
                fontWeight: 600,
                border: '1px solid rgba(239,68,68,.2)',
              }}
            >
              ⚠️ {erro}
            </div>
          )}
          {ok && (
            <div
              style={{
                background: 'rgba(16,185,129,.12)',
                color: '#34D399',
                padding: '10px 14px',
                borderRadius: 10,
                fontSize: 13,
                marginBottom: 14,
                fontWeight: 600,
                border: '1px solid rgba(16,185,129,.2)',
              }}
            >
              ✅ {ok}
            </div>
          )}

          {mode === 'login' && (
            <form
              onSubmit={doLogin}
              style={{ display: 'flex', flexDirection: 'column', gap: 16 }}
            >
              <div>
                <label style={{ ...LBL, color: '#64748B' }}>E-mail</label>
                <input
                  style={INP_DK}
                  type="email"
                  value={email}
                  onChange={(e) => setEmail(e.target.value)}
                  placeholder="seu@email.com"
                />
              </div>
              <div>
                <div
                  style={{
                    display: 'flex',
                    justifyContent: 'space-between',
                    alignItems: 'center',
                    marginBottom: 5,
                  }}
                >
                  <label style={{ ...LBL, marginBottom: 0, color: '#64748B' }}>
                    Senha
                  </label>
                  <button
                    type="button"
                    onClick={() => {
                      setMode('forgot');
                      setErro('');
                      setOk('');
                    }}
                    style={{
                      background: 'none',
                      border: 'none',
                      color: '#00BCD4',
                      fontSize: 12,
                      fontWeight: 600,
                      cursor: 'pointer',
                      fontFamily: 'inherit',
                    }}
                  >
                    Esqueci minha senha
                  </button>
                </div>
                <input
                  style={INP_DK}
                  type="password"
                  value={senha}
                  onChange={(e) => setSenha(e.target.value)}
                  placeholder="••••••••"
                />
              </div>
              <button type="submit" disabled={loading} style={BIG_BTN}>
                {loading ? 'Entrando...' : '→ Entrar no Sistema'}
              </button>
            </form>
          )}
          {mode === 'register' && (
            <form
              onSubmit={doReg}
              style={{ display: 'flex', flexDirection: 'column', gap: 14 }}
            >
              <div>
                <label style={{ ...LBL, color: '#64748B' }}>
                  Nome completo
                </label>
                <input
                  style={INP_DK}
                  value={nome}
                  onChange={(e) => setNome(e.target.value)}
                  placeholder="Ex: Maria Silva"
                />
                {nome && validarNome(nome) && (
                  <div style={{ fontSize: 11, color: '#34D399', marginTop: 4 }}>
                    ✓ Será salvo como: <strong>{formatarNome(nome)}</strong>
                  </div>
                )}
                {nome && !validarNome(nome) && (
                  <div style={{ fontSize: 11, color: '#F87171', marginTop: 4 }}>
                    ⚠️ Digite nome e sobrenome
                  </div>
                )}
              </div>
              <div>
                <label style={{ ...LBL, color: '#64748B' }}>E-mail</label>
                <input
                  style={INP_DK}
                  type="email"
                  value={email}
                  onChange={(e) => setEmail(e.target.value)}
                  placeholder="seu@email.com"
                />
              </div>
              <div>
                <label style={{ ...LBL, color: '#64748B' }}>Senha</label>
                <input
                  style={INP_DK}
                  type="password"
                  value={senha}
                  onChange={(e) => setSenha(e.target.value)}
                  placeholder="Mínimo 6 caracteres"
                />
              </div>
              <div>
                <label style={{ ...LBL, color: '#64748B' }}>
                  Confirmar senha
                </label>
                <input
                  style={INP_DK}
                  type="password"
                  value={conf}
                  onChange={(e) => setConf(e.target.value)}
                  placeholder="Repita a senha"
                />
              </div>
              <button type="submit" disabled={loading} style={BIG_BTN}>
                {loading ? 'Cadastrando...' : '→ Solicitar Acesso'}
              </button>
            </form>
          )}
          {mode === 'forgot' && (
            <form
              onSubmit={doRecuperar}
              style={{ display: 'flex', flexDirection: 'column', gap: 16 }}
            >
              <div
                style={{
                  background: 'rgba(0,188,212,.08)',
                  border: '1px solid rgba(0,188,212,.2)',
                  borderRadius: 10,
                  padding: '12px 14px',
                  fontSize: 13,
                  color: '#67E8F9',
                }}
              >
                💡 Digite o e-mail cadastrado e escolha uma nova senha.
              </div>
              <div>
                <label style={{ ...LBL, color: '#64748B' }}>
                  E-mail cadastrado
                </label>
                <input
                  style={INP_DK}
                  type="email"
                  value={emailRecup}
                  onChange={(e) => setEmailRecup(e.target.value)}
                  placeholder="seu@email.com"
                />
              </div>
              <div>
                <label style={{ ...LBL, color: '#64748B' }}>Nova senha</label>
                <input
                  style={INP_DK}
                  type="password"
                  value={novaSenha}
                  onChange={(e) => setNovaSenha(e.target.value)}
                  placeholder="Mínimo 6 caracteres"
                />
              </div>
              <div>
                <label style={{ ...LBL, color: '#64748B' }}>
                  Confirmar nova senha
                </label>
                <input
                  style={INP_DK}
                  type="password"
                  value={confNova}
                  onChange={(e) => setConfNova(e.target.value)}
                  placeholder="Repita a nova senha"
                />
              </div>
              <button type="submit" disabled={loading} style={BIG_BTN}>
                {loading ? 'Salvando...' : '🔑 Redefinir Senha'}
              </button>
              <button
                type="button"
                onClick={() => {
                  setMode('login');
                  setErro('');
                  setOk('');
                }}
                style={{
                  width: '100%',
                  padding: '11px',
                  border: '1px solid #1E293B',
                  borderRadius: 10,
                  background: 'none',
                  color: '#64748B',
                  fontSize: 14,
                  fontWeight: 600,
                  cursor: 'pointer',
                  fontFamily: 'inherit',
                }}
              >
                ← Voltar para o login
              </button>
            </form>
          )}
        </div>
      </div>
    </div>
  );
}

// ─── USUARIOS TAB ─────────────────────────────────────────────────────────────
function UsuariosTab() {
  const [usuarios, setUsuarios] = useState([]);
  const [loading, setLoading] = useState(true);
  const [perfilPendente, setPerfilPendente] = useState({}); // id -> perfil escolhido

  const carregar = useCallback(async () => {
    setLoading(true);
    try {
      const d = await sbGet('usuarios', 'order=nome.asc');
      setUsuarios(d);
    } catch (e) {
      console.error(e);
    } finally {
      setLoading(false);
    }
  }, []);

  useEffect(() => {
    carregar();
  }, [carregar]);

  async function aprovar(id) {
    const perfil = perfilPendente[id] || 'Usuário';
    await sbUpdate('usuarios', id, { status: 'ativo', perfil });
    carregar();
  }
  async function rejeitar(id) {
    await sbUpdate('usuarios', id, { status: 'rejeitado' });
    carregar();
  }
  async function excluir(id) {
    if (!window.confirm('Excluir este usuário permanentemente?')) return;
    await fetch(`${SUPA_URL}/rest/v1/usuarios?id=eq.${id}`, {
      method: 'DELETE',
      headers: H,
    });
    carregar();
  }
  async function revogar(id) {
    await sbUpdate('usuarios', id, { status: 'rejeitado' });
    carregar();
  }

  const pendentes = usuarios.filter((u) => u.status === 'pendente');
  const ativos = usuarios.filter((u) => u.status === 'ativo');
  const rejeitados = usuarios.filter((u) => u.status === 'rejeitado');

  if (loading) return <Spin />;
  return (
    <div style={{ display: 'flex', flexDirection: 'column', gap: 16 }}>
      {/* PENDENTES */}
      {pendentes.length > 0 && (
        <div
          style={{
            background: '#FEF3C7',
            border: '1px solid #FCD34D',
            borderRadius: 12,
            padding: '16px 20px',
          }}
        >
          <div
            style={{
              fontWeight: 800,
              fontSize: 14,
              color: '#92400E',
              marginBottom: 12,
            }}
          >
            ⏳ Aguardando aprovação ({pendentes.length})
          </div>
          {pendentes.map((u) => (
            <div
              key={u.id}
              style={{
                background: '#fff',
                borderRadius: 10,
                padding: '12px 16px',
                marginBottom: 8,
                display: 'flex',
                alignItems: 'center',
                justifyContent: 'space-between',
                gap: 12,
                flexWrap: 'wrap',
              }}
            >
              <div>
                <div style={{ fontWeight: 700, fontSize: 14 }}>{u.nome}</div>
                <div style={{ fontSize: 12, color: '#64748B' }}>{u.email}</div>
              </div>
              <div
                style={{
                  display: 'flex',
                  alignItems: 'center',
                  gap: 8,
                  flexWrap: 'wrap',
                }}
              >
                <div>
                  <label style={{ ...LBL, marginBottom: 3 }}>
                    Perfil ao aprovar
                  </label>
                  <select
                    style={{ ...INP, width: 160, padding: '6px 10px' }}
                    value={perfilPendente[u.id] || 'Usuário'}
                    onChange={(e) =>
                      setPerfilPendente((p) => ({
                        ...p,
                        [u.id]: e.target.value,
                      }))
                    }
                  >
                    <option value="Usuário">Usuário</option>
                    <option value="Administrador">Administrador</option>
                  </select>
                </div>
                <div
                  style={{
                    display: 'flex',
                    gap: 8,
                    alignSelf: 'flex-end',
                    paddingBottom: 2,
                  }}
                >
                  <button
                    onClick={() => aprovar(u.id)}
                    style={{
                      padding: '7px 16px',
                      background: '#10B981',
                      border: 'none',
                      borderRadius: 8,
                      color: '#fff',
                      fontWeight: 700,
                      fontSize: 12,
                      cursor: 'pointer',
                      fontFamily: 'inherit',
                    }}
                  >
                    ✓ Aprovar
                  </button>
                  <button
                    onClick={() => rejeitar(u.id)}
                    style={{
                      padding: '7px 16px',
                      background: '#EF4444',
                      border: 'none',
                      borderRadius: 8,
                      color: '#fff',
                      fontWeight: 700,
                      fontSize: 12,
                      cursor: 'pointer',
                      fontFamily: 'inherit',
                    }}
                  >
                    ✕ Rejeitar
                  </button>
                </div>
              </div>
            </div>
          ))}
        </div>
      )}

      {/* ATIVOS */}
      <div
        style={{
          background: '#fff',
          borderRadius: 14,
          boxShadow: '0 2px 8px rgba(0,0,0,.06)',
          overflow: 'hidden',
        }}
      >
        <div
          style={{
            padding: '14px 20px',
            borderBottom: '1px solid #F1F5F9',
            fontWeight: 800,
            fontSize: 14,
            color: '#0F172A',
          }}
        >
          ✅ Usuários Ativos ({ativos.length})
        </div>
        <table style={{ width: '100%', borderCollapse: 'collapse' }}>
          <thead>
            <tr>
              <TH>Nome</TH>
              <TH>E-mail</TH>
              <TH>Perfil</TH>
              <TH>Ações</TH>
            </tr>
          </thead>
          <tbody>
            {ativos.map((u, i) => (
              <tr key={u.id} style={{ background: i % 2 ? '#FAFBFC' : '#fff' }}>
                <TD style={{ fontWeight: 600 }}>{u.nome}</TD>
                <TD style={{ color: '#64748B' }}>{u.email}</TD>
                <TD>
                  <span
                    style={{
                      fontSize: 12,
                      fontWeight: 700,
                      color:
                        u.perfil === 'Administrador' ? '#8B5CF6' : '#374151',
                    }}
                  >
                    {u.perfil}
                  </span>
                </TD>
                <TD>
                  {u.email !== 'suprimentos@zettatecck.com.br' && (
                    <Btn
                      icon="🚫"
                      color="#fff"
                      bg="#EF4444"
                      onClick={() => revogar(u.id)}
                      title="Revogar acesso"
                    />
                  )}
                </TD>
              </tr>
            ))}
            {ativos.length === 0 && (
              <tr>
                <td
                  colSpan={4}
                  style={{ textAlign: 'center', padding: 24, color: '#94A3B8' }}
                >
                  Nenhum usuário ativo
                </td>
              </tr>
            )}
          </tbody>
        </table>
      </div>

      {/* REJEITADOS */}
      {rejeitados.length > 0 && (
        <div
          style={{
            background: '#fff',
            borderRadius: 14,
            boxShadow: '0 2px 8px rgba(0,0,0,.06)',
            overflow: 'hidden',
          }}
        >
          <div
            style={{
              padding: '14px 20px',
              borderBottom: '1px solid #F1F5F9',
              fontWeight: 800,
              fontSize: 14,
              color: '#0F172A',
            }}
          >
            🚫 Rejeitados / Revogados ({rejeitados.length})
          </div>
          <table style={{ width: '100%', borderCollapse: 'collapse' }}>
            <thead>
              <tr>
                <TH>Nome</TH>
                <TH>E-mail</TH>
                <TH>Ações</TH>
              </tr>
            </thead>
            <tbody>
              {rejeitados.map((u, i) => (
                <tr
                  key={u.id}
                  style={{ background: i % 2 ? '#FAFBFC' : '#fff' }}
                >
                  <TD style={{ fontWeight: 600, color: '#94A3B8' }}>
                    {u.nome}
                  </TD>
                  <TD style={{ color: '#94A3B8' }}>{u.email}</TD>
                  <TD>
                    <div style={{ display: 'flex', gap: 6 }}>
                      <Btn
                        icon="↺"
                        color="#fff"
                        bg="#10B981"
                        onClick={() => aprovar(u.id)}
                        title="Reativar como Usuário"
                      />
                      <Btn
                        icon="🗑️"
                        color="#fff"
                        bg="#EF4444"
                        onClick={() => excluir(u.id)}
                        title="Excluir permanentemente"
                      />
                    </div>
                  </TD>
                </tr>
              ))}
            </tbody>
          </table>
        </div>
      )}
    </div>
  );
}

// ─── CRUD HOOK ────────────────────────────────────────────────────────────────
function useCRUD(table, query = 'order=id.asc') {
  const [data, setData] = useState([]);
  const [loading, setLoading] = useState(true);
  const carregar = useCallback(async () => {
    setLoading(true);
    try {
      const d = await sbGet(table, query);
      setData(d);
    } catch (e) {
      console.error(e);
    } finally {
      setLoading(false);
    }
  }, [table, query]);
  useEffect(() => {
    carregar();
  }, [carregar]);
  async function inserir(obj) {
    await sbInsert(table, obj);
    carregar();
  }
  async function atualizar(id, obj) {
    await sbUpdate(table, id, obj);
    carregar();
  }
  async function deletar(id) {
    await sbDelete(table, id);
    carregar();
  }
  return { data, loading, carregar, inserir, atualizar, deletar };
}

// ─── PROJETOS ─────────────────────────────────────────────────────────────────
function ProjetosTab() {
  const {
    data: projetos,
    loading,
    inserir,
    atualizar,
    deletar,
  } = useCRUD('projetos');
  const [search, setSearch] = useState('');
  const [fSt, setFSt] = useState('all');
  const [modal, setModal] = useState(null);
  const [form, setForm] = useState({});
  const [saving, setSaving] = useState(false);
  const set = (k, v) => setForm((f) => ({ ...f, [k]: v }));
  const filt = useMemo(
    () =>
      projetos.filter((p) => {
        const q = search.toLowerCase();
        if (
          q &&
          !String(p.numero).includes(q) &&
          !p.nome.toLowerCase().includes(q) &&
          !p.cliente.toLowerCase().includes(q)
        )
          return false;
        return fSt === 'all' || p.status === fSt;
      }),
    [projetos, search, fSt]
  );
  async function save() {
    setSaving(true);
    const valor = parseFloat(form.valor) || 0;
    const cli = (form.cliente || '').toUpperCase();
    const is30 = ['NESTLÉ', 'NESTLE', 'GAROTO', 'CPW', 'PURINA'].some((x) =>
      cli.includes(x)
    );
    const pct = is30 ? 0.3 : 0.4;
    const max_compras = parseFloat((valor * pct).toFixed(2));
    const o = {
      ...form,
      valor,
      max_compras,
      numero: parseInt(form.numero) || 0,
    };
    try {
      if (modal === 'new') await inserir({ ...o, id: uid() });
      else await atualizar(o.id, o);
      setModal(null);
    } finally {
      setSaving(false);
    }
  }
  async function del(id) {
    if (window.confirm('Excluir este projeto?')) await deletar(id);
  }
  function openNew() {
    setForm({
      id: '',
      numero: '',
      nome: '',
      cliente: '',
      cidade: '',
      valor: '',
      previsao_entrega: '',
      status: 'NÃO ENTREGUE',
    });
    setModal('new');
  }

  // calcula o max_compras previsto para exibir no form
  const valorAtual = parseFloat(form.valor) || 0;
  const cliForm = (form.cliente || '').toUpperCase();
  const is30Form = ['NESTLÉ', 'NESTLE', 'GAROTO', 'CPW', 'PURINA'].some((x) =>
    cliForm.includes(x)
  );
  const pctForm = is30Form ? 30 : 40;
  const maxCalculado =
    valorAtual > 0 ? (valorAtual * (pctForm / 100)).toFixed(2) : '—';
  if (loading) return <Spin />;
  return (
    <div style={{ display: 'flex', flexDirection: 'column', gap: 14 }}>
      <div
        style={{
          background: '#fff',
          borderRadius: 12,
          padding: '12px 16px',
          display: 'flex',
          gap: 10,
          flexWrap: 'wrap',
          boxShadow: '0 1px 4px rgba(0,0,0,.06)',
        }}
      >
        <input
          value={search}
          onChange={(e) => setSearch(e.target.value)}
          placeholder="🔍 Buscar projeto, cliente..."
          style={{ ...INP, flex: 1, minWidth: 180 }}
        />
        <select
          value={fSt}
          onChange={(e) => setFSt(e.target.value)}
          style={{ ...INP, width: 'auto' }}
        >
          <option value="all">Todos</option>
          <option value="ENTREGUE">Entregue</option>
          <option value="ENTREGUE PARCIAL">Entregue Parcial</option>
          <option value="NÃO ENTREGUE">Não Entregue</option>
          <option value="SEM ENTREGA">Sem Entrega</option>
        </select>
        <button onClick={openNew} style={{ ...SAVE_BTN, padding: '8px 18px' }}>
          + Novo Projeto
        </button>
      </div>
      <div
        style={{
          background: '#fff',
          borderRadius: 14,
          boxShadow: '0 2px 8px rgba(0,0,0,.06)',
          overflow: 'hidden',
        }}
      >
        <div style={{ overflowX: 'auto' }}>
          <table style={{ width: '100%', borderCollapse: 'collapse' }}>
            <thead>
              <tr>
                <TH>Ações</TH>
                <TH>Número</TH>
                <TH>Nome</TH>
                <TH>Cliente</TH>
                <TH>Valor</TH>
                <TH>Máx. Compras</TH>
                <TH>Previsão</TH>
                <TH>Status</TH>
              </tr>
            </thead>
            <tbody>
              {filt.map((p, i) => (
                <tr
                  key={p.id}
                  style={{ background: i % 2 ? '#FAFBFC' : '#fff' }}
                  onMouseEnter={(e) =>
                    (e.currentTarget.style.background = '#EFF6FF')
                  }
                  onMouseLeave={(e) =>
                    (e.currentTarget.style.background =
                      i % 2 ? '#FAFBFC' : '#fff')
                  }
                >
                  <TD>
                    <div style={{ display: 'flex', gap: 5 }}>
                      <Btn
                        icon="✏️"
                        bg="#EFF6FF"
                        onClick={() => {
                          setForm({ ...p });
                          setModal('edit');
                        }}
                        title="Editar"
                      />
                      <Btn
                        icon="🗑️"
                        bg="#FEE2E2"
                        onClick={() => del(p.id)}
                        title="Excluir"
                      />
                    </div>
                  </TD>
                  <TD style={{ fontWeight: 800, color: '#3B82F6' }}>
                    {p.numero}
                  </TD>
                  <TD style={{ fontWeight: 500, maxWidth: 220 }}>
                    <div
                      style={{
                        overflow: 'hidden',
                        textOverflow: 'ellipsis',
                        whiteSpace: 'nowrap',
                      }}
                    >
                      {p.nome}
                    </div>
                  </TD>
                  <TD style={{ fontWeight: 600 }}>{p.cliente}</TD>
                  <TD style={{ fontWeight: 700 }}>{fmt(p.valor)}</TD>
                  <TD style={{ color: '#8B5CF6', fontWeight: 600 }}>
                    {fmt(p.max_compras)}
                  </TD>
                  <TD style={{ whiteSpace: 'nowrap' }}>
                    {fmtDate(p.previsao_entrega)}
                  </TD>
                  <TD>
                    <Badge s={p.status} />
                  </TD>
                </tr>
              ))}
              {filt.length === 0 && (
                <tr>
                  <td
                    colSpan={8}
                    style={{
                      textAlign: 'center',
                      padding: 40,
                      color: '#94A3B8',
                    }}
                  >
                    Nenhum projeto encontrado
                  </td>
                </tr>
              )}
            </tbody>
          </table>
        </div>
      </div>
      {modal && (
        <Modal
          title={modal === 'new' ? 'Novo Projeto' : 'Editar Projeto'}
          onClose={() => setModal(null)}
        >
          <div
            style={{ display: 'grid', gridTemplateColumns: '1fr 1fr', gap: 14 }}
          >
            <div style={{ gridColumn: 'span 2' }}>
              <label style={LBL}>Nome do Projeto</label>
              <input
                style={INP}
                value={form.nome || ''}
                onChange={(e) => set('nome', e.target.value)}
              />
            </div>
            <div>
              <label style={LBL}>Número</label>
              <input
                style={INP}
                value={form.numero || ''}
                onChange={(e) => set('numero', e.target.value)}
              />
            </div>
            <div>
              <label style={LBL}>Cliente</label>
              <input
                style={INP}
                value={form.cliente || ''}
                onChange={(e) => set('cliente', e.target.value)}
                placeholder="Ex: NESTLÉ, GAROTO..."
              />
            </div>
            <div>
              <label style={LBL}>Cidade</label>
              <input
                style={INP}
                value={form.cidade || ''}
                onChange={(e) => set('cidade', e.target.value)}
              />
            </div>
            <div>
              <label style={LBL}>Status</label>
              <select
                style={INP}
                value={form.status || 'NÃO ENTREGUE'}
                onChange={(e) => set('status', e.target.value)}
              >
                <option>ENTREGUE</option>
                <option>ENTREGUE PARCIAL</option>
                <option>NÃO ENTREGUE</option>
                <option>SEM ENTREGA</option>
              </select>
            </div>
            <div>
              <label style={LBL}>Valor do Projeto (R$)</label>
              <input
                style={INP}
                type="number"
                value={form.valor || ''}
                onChange={(e) => set('valor', e.target.value)}
                placeholder="0,00"
              />
            </div>
            <div>
              <label style={LBL}>
                Máx. Compras (calculado automaticamente)
              </label>
              <div
                style={{
                  ...INP,
                  background: '#F0FDF4',
                  border: '1.5px solid #86EFAC',
                  color: '#065F46',
                  fontWeight: 700,
                  display: 'flex',
                  alignItems: 'center',
                  justifyContent: 'space-between',
                }}
              >
                <span>
                  {valorAtual > 0
                    ? `R$ ${Number(maxCalculado).toLocaleString('pt-BR', {
                        minimumFractionDigits: 2,
                      })}`
                    : '—'}
                </span>
                <span
                  style={{
                    fontSize: 11,
                    fontWeight: 600,
                    background: is30Form ? '#DCFCE7' : '#DBEAFE',
                    color: is30Form ? '#166534' : '#1E40AF',
                    padding: '2px 8px',
                    borderRadius: 10,
                  }}
                >
                  {is30Form ? '30%' : '40%'}
                </span>
              </div>
              <div style={{ fontSize: 11, color: '#64748B', marginTop: 4 }}>
                💡 Nestlé, Garoto, CPW, Purina = 30% · Outros = 40% do valor do
                projeto
              </div>
            </div>
            <div style={{ gridColumn: 'span 2' }}>
              <label style={LBL}>Previsão de Entrega</label>
              <input
                style={INP}
                type="date"
                value={form.previsao_entrega || ''}
                onChange={(e) => set('previsao_entrega', e.target.value)}
              />
            </div>
          </div>
          <div
            style={{
              display: 'flex',
              gap: 10,
              justifyContent: 'flex-end',
              marginTop: 20,
            }}
          >
            <button onClick={() => setModal(null)} style={CANCEL_BTN}>
              Cancelar
            </button>
            <button
              onClick={save}
              disabled={saving}
              style={{ ...SAVE_BTN, opacity: saving ? 0.7 : 1 }}
            >
              {saving ? 'Salvando...' : 'Salvar'}
            </button>
          </div>
        </Modal>
      )}
    </div>
  );
}

// ─── PEDIDOS ──────────────────────────────────────────────────────────────────
function PedidosTab() {
  const {
    data: pedidos,
    loading,
    inserir,
    atualizar,
    deletar,
  } = useCRUD('pedidos');
  const { data: projetos } = useCRUD('projetos', 'order=numero.asc');
  const { data: fornecedores } = useCRUD('fornecedores', 'order=nome.asc');
  const [search, setSearch] = useState('');
  const [fSt, setFSt] = useState('all');
  const [fPd, setFPd] = useState('all');
  const [modal, setModal] = useState(null);
  const [form, setForm] = useState({});
  const [saving, setSaving] = useState(false);
  const set = (k, v) => setForm((f) => ({ ...f, [k]: v }));
  const filt = useMemo(
    () =>
      pedidos.filter((p) => {
        const q = search.toLowerCase();
        if (
          q &&
          !String(p.numero).includes(q) &&
          !p.fornecedor.toLowerCase().includes(q) &&
          !String(p.projeto || '').includes(q)
        )
          return false;
        if (fSt !== 'all' && p.status !== fSt) return false;
        if (fPd !== 'all' && p.pendencia !== fPd) return false;
        return true;
      }),
    [pedidos, search, fSt, fPd]
  );
  async function save() {
    setSaving(true);
    // serializa itens pendentes em JSON para salvar no campo obs_itens
    const itensPendentes = form.itensPendentes || [];
    const o = {
      ...form,
      valor: parseFloat(form.valor) || 0,
      itens_pendentes:
        itensPendentes.length > 0 ? JSON.stringify(itensPendentes) : null,
    };
    delete o.itensPendentes;
    try {
      if (modal === 'new') await inserir({ ...o, id: uid() });
      else await atualizar(o.id, o);
      setModal(null);
    } finally {
      setSaving(false);
    }
  }
  async function del(id) {
    if (window.confirm('Excluir este pedido?')) await deletar(id);
  }
  function openNew() {
    setForm({
      id: '',
      numero: '',
      fornecedor: '',
      projeto: '',
      valor: '',
      status: 'Aguardando',
      nfe: '',
      data_fatura: '',
      data_entrega: '',
      pendencia: 'Não',
      obs: '',
      itensPendentes: [],
    });
    setModal('new');
  }

  if (loading) return <Spin />;

  const projSel = projetos.find(
    (p) => String(p.numero) === String(form.projeto)
  );

  return (
    <div style={{ display: 'flex', flexDirection: 'column', gap: 14 }}>
      <div
        style={{
          background: '#fff',
          borderRadius: 12,
          padding: '12px 16px',
          display: 'flex',
          gap: 10,
          flexWrap: 'wrap',
          boxShadow: '0 1px 4px rgba(0,0,0,.06)',
        }}
      >
        <input
          value={search}
          onChange={(e) => setSearch(e.target.value)}
          placeholder="🔍 Buscar nº, fornecedor, projeto..."
          style={{ ...INP, flex: 1, minWidth: 180 }}
        />
        <select
          value={fSt}
          onChange={(e) => setFSt(e.target.value)}
          style={{ ...INP, width: 'auto' }}
        >
          <option value="all">Todos Status</option>
          {[
            'Concluído',
            'Aguardando',
            'Faturado Inicial',
            'Entregue Parcial',
          ].map((s) => (
            <option key={s}>{s}</option>
          ))}
        </select>
        <select
          value={fPd}
          onChange={(e) => setFPd(e.target.value)}
          style={{ ...INP, width: 'auto' }}
        >
          <option value="all">Pendência: Todas</option>
          <option value="Sim">Com Pendência</option>
          <option value="Não">Sem Pendência</option>
        </select>
        <button onClick={openNew} style={{ ...SAVE_BTN, padding: '8px 18px' }}>
          + Novo Pedido
        </button>
      </div>
      <div
        style={{
          background: '#fff',
          borderRadius: 14,
          boxShadow: '0 2px 8px rgba(0,0,0,.06)',
          overflow: 'hidden',
        }}
      >
        <div style={{ overflowX: 'auto' }}>
          <table style={{ width: '100%', borderCollapse: 'collapse' }}>
            <thead>
              <tr>
                <TH>Ações</TH>
                <TH>Nº</TH>
                <TH>Fornecedor</TH>
                <TH>Projeto</TH>
                <TH>Valor</TH>
                <TH>Status</TH>
                <TH>NF-e</TH>
                <TH>Prazo Fatura</TH>
                <TH>Prazo Entrega</TH>
                <TH>Pendência</TH>
                <TH>Itens Pendentes</TH>
                <TH>Obs</TH>
              </tr>
            </thead>
            <tbody>
              {filt.map((p, i) => {
                const itens = p.itens_pendentes
                  ? JSON.parse(p.itens_pendentes)
                  : [];
                const itensPend = itens.filter((it) => !it.faturado);
                const itensFat = itens.filter((it) => it.faturado);
                return (
                  <tr
                    key={p.id}
                    style={{ background: i % 2 ? '#FAFBFC' : '#fff' }}
                    onMouseEnter={(e) =>
                      (e.currentTarget.style.background = '#EFF6FF')
                    }
                    onMouseLeave={(e) =>
                      (e.currentTarget.style.background =
                        i % 2 ? '#FAFBFC' : '#fff')
                    }
                  >
                    <TD>
                      <div style={{ display: 'flex', gap: 5 }}>
                        <Btn
                          icon="✏️"
                          bg="#EFF6FF"
                          onClick={() => {
                            const itens = p.itens_pendentes
                              ? JSON.parse(p.itens_pendentes)
                              : [];
                            setForm({ ...p, itensPendentes: itens });
                            setModal('edit');
                          }}
                          title="Editar"
                        />
                        <Btn
                          icon="🗑️"
                          bg="#FEE2E2"
                          onClick={() => del(p.id)}
                          title="Excluir"
                        />
                      </div>
                    </TD>
                    <TD style={{ fontWeight: 800, color: '#8B5CF6' }}>
                      {p.numero}
                    </TD>
                    <TD style={{ fontWeight: 600 }}>{p.fornecedor}</TD>
                    <TD style={{ fontWeight: 600, color: '#3B82F6' }}>
                      {p.projeto || 'GERAIS'}
                    </TD>
                    <TD style={{ fontWeight: 700 }}>{fmt(p.valor)}</TD>
                    <TD>
                      <Badge s={p.status} />
                    </TD>
                    <TD style={{ color: '#64748B', fontSize: 11 }}>
                      {p.nfe || '—'}
                    </TD>
                    <TD style={{ whiteSpace: 'nowrap' }}>
                      {fmtDate(p.data_fatura)}
                    </TD>
                    <TD style={{ whiteSpace: 'nowrap' }}>
                      {fmtDate(p.data_entrega)}
                    </TD>
                    <TD
                      style={{
                        fontWeight: 700,
                        color: (() => {
                          if (p.pendencia !== 'Sim') return '#10B981';
                          if (itens.length === 0) return '#10B981'; // sem itens = entregue
                          if (itens.every((it) => it.faturado))
                            return '#10B981'; // todos faturados = verde
                          return '#EF4444'; // ainda tem pendentes = vermelho
                        })(),
                      }}
                    >
                      {p.pendencia}
                    </TD>
                    <TD style={{ minWidth: 200 }}>
                      {(() => {
                        const todosEntregues =
                          itens.length > 0 && itens.every((it) => it.faturado);
                        if (itens.length === 0 && p.pendencia === 'Sim') {
                          return (
                            <span
                              style={{
                                fontSize: 11,
                                fontWeight: 700,
                                color: '#10B981',
                                background: '#D1FAE5',
                                padding: '3px 10px',
                                borderRadius: 6,
                                border: '1px solid #6EE7B7',
                              }}
                            >
                              ✅ Pendência(s) entregue(s)
                            </span>
                          );
                        }
                        if (itens.length === 0)
                          return (
                            <span style={{ color: '#94A3B8', fontSize: 11 }}>
                              —
                            </span>
                          );
                        if (todosEntregues && p.pendencia === 'Sim') {
                          return (
                            <div
                              style={{
                                display: 'flex',
                                flexDirection: 'column',
                                gap: 4,
                              }}
                            >
                              {itens.map((it, idx) => (
                                <div
                                  key={idx}
                                  style={{
                                    display: 'flex',
                                    alignItems: 'center',
                                    gap: 6,
                                    padding: '4px 8px',
                                    borderRadius: 7,
                                    background: '#D1FAE5',
                                    border: '1px solid #6EE7B7',
                                  }}
                                >
                                  <span
                                    style={{
                                      fontSize: 11,
                                      fontWeight: 700,
                                      color: '#065F46',
                                      flex: 1,
                                    }}
                                  >
                                    {it.codigo}
                                  </span>
                                  <span
                                    style={{ fontSize: 11, color: '#065F46' }}
                                  >
                                    x{it.quantidade}
                                  </span>
                                  <span
                                    style={{
                                      fontSize: 11,
                                      color: '#10B981',
                                      fontWeight: 700,
                                    }}
                                  >
                                    ✓ {fmtDate(it.dataFaturamento)}
                                  </span>
                                </div>
                              ))}
                              <span
                                style={{
                                  fontSize: 11,
                                  fontWeight: 700,
                                  color: '#10B981',
                                  marginTop: 2,
                                }}
                              >
                                ✅ Pendência(s) entregue(s)
                              </span>
                            </div>
                          );
                        }
                        return (
                          <div
                            style={{
                              display: 'flex',
                              flexDirection: 'column',
                              gap: 4,
                            }}
                          >
                            {itens.map((it, idx) => {
                              const hoje = new Date();
                              hoje.setHours(0, 0, 0, 0);
                              const prazo = it.prazoPrev
                                ? parseLocal(it.prazoPrev)
                                : null;
                              const vencido =
                                !it.faturado &&
                                !it.emAtraso &&
                                prazo &&
                                prazo < hoje;
                              const emAtraso = !it.faturado && it.emAtraso;
                              const bg = it.faturado
                                ? '#D1FAE5'
                                : emAtraso
                                ? '#FEE2E2'
                                : vencido
                                ? '#FEE2E2'
                                : '#FEF3C7';
                              const border = it.faturado
                                ? '#6EE7B7'
                                : emAtraso
                                ? '#FCA5A5'
                                : vencido
                                ? '#FCA5A5'
                                : '#FCD34D';
                              const textColor = it.faturado
                                ? '#065F46'
                                : emAtraso
                                ? '#991B1B'
                                : vencido
                                ? '#991B1B'
                                : '#92400E';
                              return (
                                <div
                                  key={idx}
                                  style={{
                                    display: 'flex',
                                    alignItems: 'center',
                                    gap: 6,
                                    padding: '4px 8px',
                                    borderRadius: 7,
                                    background: bg,
                                    border: `1px solid ${border}`,
                                  }}
                                >
                                  <span
                                    style={{
                                      fontSize: 11,
                                      fontWeight: 700,
                                      color: textColor,
                                      flex: 1,
                                      overflow: 'hidden',
                                      textOverflow: 'ellipsis',
                                      whiteSpace: 'nowrap',
                                    }}
                                    title={it.codigo}
                                  >
                                    {it.codigo}
                                  </span>
                                  <span
                                    style={{
                                      fontSize: 11,
                                      color: textColor,
                                      flexShrink: 0,
                                    }}
                                  >
                                    x{it.quantidade}
                                  </span>
                                  <span
                                    style={{
                                      fontSize: 11,
                                      fontWeight: 700,
                                      color: textColor,
                                      flexShrink: 0,
                                    }}
                                  >
                                    {it.faturado
                                      ? `✓ ${fmtDate(it.dataFaturamento)}`
                                      : emAtraso
                                      ? '🔴 Conf. nova data'
                                      : vencido
                                      ? '🔴 Em atraso'
                                      : `⏳ ${
                                          it.prazoPrev
                                            ? 'Prev. ' + fmtDate(it.prazoPrev)
                                            : 's/prazo'
                                        }`}
                                  </span>
                                </div>
                              );
                            })}
                            <div
                              style={{
                                fontSize: 10,
                                color: '#64748B',
                                marginTop: 1,
                              }}
                            >
                              {itensFat.length}/{itens.length} faturado
                              {itensFat.length !== 1 ? 's' : ''}
                            </div>
                          </div>
                        );
                      })()}
                    </TD>
                    <TD
                      style={{ maxWidth: 140, color: '#64748B', fontSize: 11 }}
                    >
                      <div
                        style={{
                          overflow: 'hidden',
                          textOverflow: 'ellipsis',
                          whiteSpace: 'nowrap',
                        }}
                        title={p.obs}
                      >
                        {p.obs}
                      </div>
                    </TD>
                  </tr>
                );
              })}
              {filt.length === 0 && (
                <tr>
                  <td
                    colSpan={12}
                    style={{
                      textAlign: 'center',
                      padding: 40,
                      color: '#94A3B8',
                    }}
                  >
                    Nenhum pedido encontrado
                  </td>
                </tr>
              )}
            </tbody>
          </table>
        </div>
        <div
          style={{
            padding: '10px 16px',
            borderTop: '1px solid #F1F5F9',
            display: 'flex',
            justifyContent: 'flex-end',
          }}
        >
          <span style={{ fontSize: 12, fontWeight: 700 }}>
            Total filtrado: {fmt(filt.reduce((s, p) => s + p.valor, 0))}
          </span>
        </div>
      </div>
      {modal && (
        <Modal
          title={modal === 'new' ? 'Novo Pedido de Compra' : 'Editar Pedido'}
          onClose={() => setModal(null)}
          wide
        >
          <div
            style={{ display: 'grid', gridTemplateColumns: '1fr 1fr', gap: 14 }}
          >
            <div>
              <label style={LBL}>Nº Pedido</label>
              <input
                style={INP}
                value={form.numero || ''}
                onChange={(e) => set('numero', e.target.value)}
              />
            </div>
            <div>
              <label style={LBL}>Fornecedor</label>
              <select
                style={INP}
                value={form.fornecedor || ''}
                onChange={(e) => set('fornecedor', e.target.value)}
              >
                <option value="">-- Selecione --</option>
                {fornecedores.map((f) => (
                  <option key={f.id} value={f.nome}>
                    {f.nome}
                  </option>
                ))}
              </select>
            </div>
            <div>
              <label style={LBL}>Projeto</label>
              <select
                style={INP}
                value={form.projeto || ''}
                onChange={(e) => set('projeto', e.target.value)}
              >
                <option value="">-- Selecione --</option>
                <option value="GERAIS">GERAIS</option>
                {projetos
                  .sort((a, b) => a.numero - b.numero)
                  .map((p) => (
                    <option key={p.id} value={p.numero}>
                      {p.numero} — {p.nome} ({p.cliente})
                    </option>
                  ))}
              </select>
              {projSel && (
                <div
                  style={{
                    fontSize: 11,
                    color: '#3B82F6',
                    marginTop: 4,
                    fontWeight: 600,
                  }}
                >
                  📁 {projSel.nome} · {projSel.cliente}
                </div>
              )}
            </div>
            <div>
              <label style={LBL}>Valor (R$)</label>
              <input
                style={INP}
                type="number"
                value={form.valor || ''}
                onChange={(e) => set('valor', e.target.value)}
              />
            </div>
            <div>
              <label style={LBL}>Status</label>
              <select
                style={INP}
                value={form.status || 'Aguardando'}
                onChange={(e) => set('status', e.target.value)}
              >
                {[
                  'Concluído',
                  'Aguardando',
                  'Faturado Inicial',
                  'Entregue Parcial',
                ].map((s) => (
                  <option key={s}>{s}</option>
                ))}
              </select>
            </div>
            <div>
              <label style={LBL}>NF-e</label>
              <input
                style={INP}
                value={form.nfe || ''}
                onChange={(e) => set('nfe', e.target.value)}
              />
            </div>
            <div>
              <label style={LBL}>
                {form.status === 'Faturado Inicial' ||
                form.status === 'Entregue Parcial' ||
                form.status === 'Concluído'
                  ? '📅 Data de Faturamento'
                  : 'Prazo de Faturamento'}
              </label>
              <input
                style={{
                  ...INP,
                  borderColor:
                    form.status === 'Faturado Inicial' ||
                    form.status === 'Entregue Parcial' ||
                    form.status === 'Concluído'
                      ? '#00BCD4'
                      : '#E2E8F0',
                }}
                type="date"
                value={form.data_fatura || ''}
                onChange={(e) => set('data_fatura', e.target.value)}
              />
              {(form.status === 'Faturado Inicial' ||
                form.status === 'Entregue Parcial' ||
                form.status === 'Concluído') && (
                <div style={{ fontSize: 11, color: '#0E7490', marginTop: 3 }}>
                  💡 Informe a data real em que foi faturado
                </div>
              )}
            </div>
            <div>
              <label style={LBL}>
                {form.status === 'Concluído'
                  ? '📅 Data de Entrega'
                  : form.status === 'Entregue Parcial'
                  ? '📅 Data da Entrega Parcial'
                  : 'Prazo de Entrega'}
              </label>
              <input
                style={{
                  ...INP,
                  borderColor:
                    form.status === 'Concluído' ||
                    form.status === 'Entregue Parcial'
                      ? '#00BCD4'
                      : '#E2E8F0',
                }}
                type="date"
                value={form.data_entrega || ''}
                onChange={(e) => set('data_entrega', e.target.value)}
              />
              {(form.status === 'Concluído' ||
                form.status === 'Entregue Parcial') && (
                <div style={{ fontSize: 11, color: '#0E7490', marginTop: 3 }}>
                  💡 Informe a data real de entrega
                </div>
              )}
            </div>
            <div>
              <label style={LBL}>Pendência</label>
              <select
                style={INP}
                value={form.pendencia || 'Não'}
                onChange={(e) => set('pendencia', e.target.value)}
              >
                <option>Não</option>
                <option>Sim</option>
              </select>
            </div>
            <div style={{ gridColumn: 'span 2' }}>
              <label style={LBL}>Observações</label>
              <textarea
                style={{ ...INP, resize: 'vertical' }}
                rows={2}
                value={form.obs || ''}
                onChange={(e) => set('obs', e.target.value)}
              />
            </div>
            {/* ITENS PENDENTES — aparece só quando pendencia = Sim */}
            {form.pendencia === 'Sim' && (
              <div
                style={{
                  gridColumn: 'span 2',
                  background: '#FFF7ED',
                  border: '1.5px solid #FED7AA',
                  borderRadius: 12,
                  padding: '14px 16px',
                }}
              >
                <div
                  style={{
                    display: 'flex',
                    justifyContent: 'space-between',
                    alignItems: 'center',
                    marginBottom: 12,
                  }}
                >
                  <label style={{ ...LBL, color: '#92400E', marginBottom: 0 }}>
                    🔴 Itens Pendentes
                  </label>
                  <button
                    type="button"
                    onClick={() => {
                      const itens = form.itensPendentes || [];
                      set('itensPendentes', [
                        ...itens,
                        {
                          id: uid(),
                          codigo: '',
                          quantidade: '',
                          prazoPrev: '',
                        },
                      ]);
                    }}
                    style={{
                      padding: '5px 14px',
                      background: '#F97316',
                      border: 'none',
                      borderRadius: 7,
                      color: '#fff',
                      fontWeight: 700,
                      fontSize: 12,
                      cursor: 'pointer',
                      fontFamily: 'inherit',
                    }}
                  >
                    + Adicionar Item
                  </button>
                </div>
                {(!form.itensPendentes || form.itensPendentes.length === 0) && (
                  <div
                    style={{
                      textAlign: 'center',
                      color: '#F97316',
                      fontSize: 12,
                      padding: '8px 0',
                      fontStyle: 'italic',
                    }}
                  >
                    Clique em "+ Adicionar Item" para cadastrar os itens
                    pendentes
                  </div>
                )}
                {(form.itensPendentes || []).map((item, idx) => (
                  <div
                    key={item.id || idx}
                    style={{
                      background: item.faturado ? '#F0FDF4' : '#fff',
                      border: `1.5px solid ${
                        item.faturado ? '#86EFAC' : '#FED7AA'
                      }`,
                      borderRadius: 10,
                      padding: '10px 12px',
                      marginBottom: 8,
                    }}
                  >
                    {/* linha 1: código + qtd + prazo */}
                    <div
                      style={{
                        display: 'grid',
                        gridTemplateColumns: '1fr 80px 140px 32px',
                        gap: 8,
                        alignItems: 'end',
                        marginBottom: item.faturado ? 0 : 0,
                      }}
                    >
                      <div>
                        {idx === 0 && (
                          <div
                            style={{
                              fontSize: 10,
                              fontWeight: 700,
                              color: '#92400E',
                              textTransform: 'uppercase',
                              letterSpacing: 0.4,
                              marginBottom: 4,
                            }}
                          >
                            Código do Item
                          </div>
                        )}
                        <input
                          style={{ ...INP, background: '#fff', fontSize: 12 }}
                          value={item.codigo}
                          onChange={(e) => {
                            const arr = [...(form.itensPendentes || [])];
                            arr[idx] = { ...arr[idx], codigo: e.target.value };
                            set('itensPendentes', arr);
                          }}
                          placeholder="Ex: 3VA1140-4EF32"
                          disabled={item.faturado}
                        />
                      </div>
                      <div>
                        {idx === 0 && (
                          <div
                            style={{
                              fontSize: 10,
                              fontWeight: 700,
                              color: '#92400E',
                              textTransform: 'uppercase',
                              letterSpacing: 0.4,
                              marginBottom: 4,
                            }}
                          >
                            Qtd
                          </div>
                        )}
                        <input
                          style={{ ...INP, background: '#fff', fontSize: 12 }}
                          type="number"
                          min="1"
                          value={item.quantidade}
                          onChange={(e) => {
                            const arr = [...(form.itensPendentes || [])];
                            arr[idx] = {
                              ...arr[idx],
                              quantidade: e.target.value,
                            };
                            set('itensPendentes', arr);
                          }}
                          placeholder="1"
                          disabled={item.faturado}
                        />
                      </div>
                      <div>
                        {idx === 0 && (
                          <div
                            style={{
                              fontSize: 10,
                              fontWeight: 700,
                              color: '#92400E',
                              textTransform: 'uppercase',
                              letterSpacing: 0.4,
                              marginBottom: 4,
                            }}
                          >
                            Prazo Fat. Previsto
                          </div>
                        )}
                        <input
                          style={{ ...INP, background: '#fff', fontSize: 12 }}
                          type="date"
                          value={item.prazoPrev || ''}
                          onChange={(e) => {
                            const arr = [...(form.itensPendentes || [])];
                            arr[idx] = {
                              ...arr[idx],
                              prazoPrev: e.target.value,
                            };
                            set('itensPendentes', arr);
                          }}
                          disabled={item.faturado}
                        />
                      </div>
                      <button
                        type="button"
                        onClick={() => {
                          const arr = (form.itensPendentes || []).filter(
                            (_, i) => i !== idx
                          );
                          set('itensPendentes', arr);
                        }}
                        style={{
                          width: 32,
                          height: 32,
                          background: '#FEE2E2',
                          border: 'none',
                          borderRadius: 7,
                          color: '#EF4444',
                          fontWeight: 700,
                          cursor: 'pointer',
                          fontSize: 14,
                          marginTop: idx === 0 ? 18 : 0,
                        }}
                      >
                        ✕
                      </button>
                    </div>
                    {/* linha 2: marcar como faturado */}
                    <div
                      style={{
                        marginTop: 8,
                        display: 'flex',
                        alignItems: 'center',
                        gap: 10,
                        flexWrap: 'wrap',
                      }}
                    >
                      {!item.faturado ? (
                        <>
                          {item.prazoPrev &&
                          parseLocal(item.prazoPrev) <
                            new Date(new Date().setHours(0, 0, 0, 0)) ? (
                            <span
                              style={{
                                fontSize: 11,
                                color: '#EF4444',
                                fontWeight: 700,
                              }}
                            >
                              🔴 Em atraso desde {fmtDate(item.prazoPrev)}
                            </span>
                          ) : (
                            <span
                              style={{
                                fontSize: 11,
                                color: '#F59E0B',
                                fontWeight: 600,
                              }}
                            >
                              ⏳ Aguardando faturamento
                            </span>
                          )}
                          <div
                            style={{
                              display: 'flex',
                              alignItems: 'center',
                              gap: 6,
                              marginLeft: 'auto',
                              flexWrap: 'wrap',
                            }}
                          >
                            {/* botão Em Atraso */}
                            {!item.emAtraso ? (
                              <button
                                type="button"
                                onClick={() => {
                                  const arr = [...(form.itensPendentes || [])];
                                  arr[idx] = { ...arr[idx], emAtraso: true };
                                  set('itensPendentes', arr);
                                }}
                                style={{
                                  padding: '4px 10px',
                                  background: '#FEF3C7',
                                  border: '1px solid #FCD34D',
                                  borderRadius: 6,
                                  color: '#92400E',
                                  fontWeight: 700,
                                  fontSize: 11,
                                  cursor: 'pointer',
                                  fontFamily: 'inherit',
                                  whiteSpace: 'nowrap',
                                }}
                              >
                                📋 Em Atraso
                              </button>
                            ) : (
                              <button
                                type="button"
                                onClick={() => {
                                  const arr = [...(form.itensPendentes || [])];
                                  arr[idx] = { ...arr[idx], emAtraso: false };
                                  set('itensPendentes', arr);
                                }}
                                style={{
                                  padding: '4px 10px',
                                  background: '#FEE2E2',
                                  border: '1px solid #FCA5A5',
                                  borderRadius: 6,
                                  color: '#991B1B',
                                  fontWeight: 700,
                                  fontSize: 11,
                                  cursor: 'pointer',
                                  fontFamily: 'inherit',
                                  whiteSpace: 'nowrap',
                                }}
                              >
                                🔴 Confirmando Nova Data
                              </button>
                            )}
                            <input
                              type="date"
                              value={item._dataFat || ''}
                              onChange={(e) => {
                                const arr = [...(form.itensPendentes || [])];
                                arr[idx] = {
                                  ...arr[idx],
                                  _dataFat: e.target.value,
                                };
                                set('itensPendentes', arr);
                              }}
                              style={{
                                ...INP,
                                width: 140,
                                fontSize: 11,
                                padding: '5px 8px',
                              }}
                              placeholder="Data da NF"
                            />
                            <button
                              type="button"
                              disabled={!item._dataFat}
                              onClick={() => {
                                const arr = [...(form.itensPendentes || [])];
                                arr[idx] = {
                                  ...arr[idx],
                                  faturado: true,
                                  dataFaturamento: arr[idx]._dataFat,
                                  emAtraso: false,
                                  _dataFat: undefined,
                                };
                                set('itensPendentes', arr);
                              }}
                              style={{
                                padding: '5px 12px',
                                background: item._dataFat
                                  ? '#10B981'
                                  : '#E2E8F0',
                                border: 'none',
                                borderRadius: 6,
                                color: item._dataFat ? '#fff' : '#94A3B8',
                                fontWeight: 700,
                                fontSize: 11,
                                cursor: item._dataFat
                                  ? 'pointer'
                                  : 'not-allowed',
                                fontFamily: 'inherit',
                                whiteSpace: 'nowrap',
                              }}
                            >
                              ✓ Confirmar Faturamento
                            </button>
                          </div>
                        </>
                      ) : (
                        <>
                          <span
                            style={{
                              fontSize: 11,
                              color: '#10B981',
                              fontWeight: 700,
                            }}
                          >
                            ✅ Faturado em {fmtDate(item.dataFaturamento)}
                          </span>
                          <button
                            type="button"
                            onClick={() => {
                              const arr = [...(form.itensPendentes || [])];
                              arr[idx] = {
                                ...arr[idx],
                                faturado: false,
                                dataFaturamento: null,
                                _dataFat: '',
                              };
                              set('itensPendentes', arr);
                            }}
                            style={{
                              padding: '4px 12px',
                              background: '#F1F5F9',
                              border: 'none',
                              borderRadius: 6,
                              color: '#64748B',
                              fontWeight: 600,
                              fontSize: 11,
                              cursor: 'pointer',
                              fontFamily: 'inherit',
                            }}
                          >
                            ↩ Desfazer
                          </button>
                        </>
                      )}
                    </div>
                  </div>
                ))}
                {(form.itensPendentes || []).length > 0 && (
                  <div
                    style={{
                      fontSize: 11,
                      color: '#92400E',
                      marginTop: 6,
                      fontWeight: 600,
                    }}
                  >
                    {(form.itensPendentes || []).length} item(s) pendente(s)
                    cadastrado(s)
                  </div>
                )}
              </div>
            )}
          </div>
          <div
            style={{
              display: 'flex',
              gap: 10,
              justifyContent: 'flex-end',
              marginTop: 18,
            }}
          >
            <button onClick={() => setModal(null)} style={CANCEL_BTN}>
              Cancelar
            </button>
            <button
              onClick={save}
              disabled={saving}
              style={{ ...SAVE_BTN, opacity: saving ? 0.7 : 1 }}
            >
              {saving ? 'Salvando...' : 'Salvar'}
            </button>
          </div>
        </Modal>
      )}
    </div>
  );
}

// ─── FORNECEDORES ─────────────────────────────────────────────────────────────
function FornecedoresTab() {
  const {
    data: fornecedores,
    loading,
    inserir,
    atualizar,
    deletar,
  } = useCRUD('fornecedores');
  const [modal, setModal] = useState(null);
  const [form, setForm] = useState({});
  const [saving, setSaving] = useState(false);
  const set = (k, v) => setForm((f) => ({ ...f, [k]: v }));
  async function save() {
    setSaving(true);
    const obj = { ...form, nome: (form.nome || '').toUpperCase() };
    try {
      if (modal === 'new') await inserir({ ...obj, id: uid() });
      else await atualizar(obj.id, obj);
      setModal(null);
    } finally {
      setSaving(false);
    }
  }
  async function del(id) {
    if (window.confirm('Excluir este fornecedor?')) await deletar(id);
  }
  if (loading) return <Spin />;
  return (
    <div style={{ display: 'flex', flexDirection: 'column', gap: 14 }}>
      <div style={{ display: 'flex', justifyContent: 'flex-end' }}>
        <button
          onClick={() => {
            setForm({
              id: '',
              nome: '',
              responsavel: '',
              telefone: '',
              email: '',
              categoria: '',
            });
            setModal('new');
          }}
          style={{ ...SAVE_BTN, padding: '9px 20px' }}
        >
          + Novo Fornecedor
        </button>
      </div>
      <div
        style={{
          background: '#fff',
          borderRadius: 14,
          boxShadow: '0 2px 8px rgba(0,0,0,.06)',
          overflow: 'hidden',
        }}
      >
        <table style={{ width: '100%', borderCollapse: 'collapse' }}>
          <thead>
            <tr>
              <TH>Ações</TH>
              <TH>Empresa</TH>
              <TH>Responsável</TH>
              <TH>Telefone</TH>
              <TH>E-mail</TH>
            </tr>
          </thead>
          <tbody>
            {fornecedores.map((f, i) => (
              <tr
                key={f.id}
                style={{ background: i % 2 ? '#FAFBFC' : '#fff' }}
                onMouseEnter={(e) =>
                  (e.currentTarget.style.background = '#EFF6FF')
                }
                onMouseLeave={(e) =>
                  (e.currentTarget.style.background =
                    i % 2 ? '#FAFBFC' : '#fff')
                }
              >
                <TD>
                  <div style={{ display: 'flex', gap: 5 }}>
                    <Btn
                      icon="✏️"
                      bg="#EFF6FF"
                      onClick={() => {
                        setForm({ ...f });
                        setModal('edit');
                      }}
                      title="Editar"
                    />
                    <Btn
                      icon="🗑️"
                      bg="#FEE2E2"
                      onClick={() => del(f.id)}
                      title="Excluir"
                    />
                  </div>
                </TD>
                <TD style={{ fontWeight: 700 }}>{f.nome}</TD>
                <TD>{f.responsavel}</TD>
                <TD style={{ fontFamily: 'monospace' }}>{f.telefone}</TD>
                <TD>
                  {f.email && f.email !== '—' ? (
                    <a
                      href={`mailto:${f.email}`}
                      style={{ color: '#3B82F6', textDecoration: 'none' }}
                    >
                      {f.email}
                    </a>
                  ) : (
                    '—'
                  )}
                </TD>
              </tr>
            ))}
            {fornecedores.length === 0 && (
              <tr>
                <td
                  colSpan={5}
                  style={{ textAlign: 'center', padding: 40, color: '#94A3B8' }}
                >
                  Nenhum fornecedor cadastrado
                </td>
              </tr>
            )}
          </tbody>
        </table>
      </div>
      {modal && (
        <Modal
          title={modal === 'new' ? 'Novo Fornecedor' : 'Editar Fornecedor'}
          onClose={() => setModal(null)}
        >
          <div
            style={{ display: 'grid', gridTemplateColumns: '1fr 1fr', gap: 14 }}
          >
            <div style={{ gridColumn: 'span 2' }}>
              <label style={LBL}>Nome da Empresa</label>
              <input
                style={INP}
                value={form.nome || ''}
                onChange={(e) => set('nome', e.target.value)}
              />
            </div>
            <div>
              <label style={LBL}>Responsável</label>
              <input
                style={INP}
                value={form.responsavel || ''}
                onChange={(e) => set('responsavel', e.target.value)}
              />
            </div>
            <div>
              <label style={LBL}>Telefone</label>
              <input
                style={INP}
                value={form.telefone || ''}
                onChange={(e) => set('telefone', e.target.value)}
              />
            </div>
            <div style={{ gridColumn: 'span 2' }}>
              <label style={LBL}>E-mail</label>
              <input
                style={INP}
                type="email"
                value={form.email || ''}
                onChange={(e) => set('email', e.target.value)}
              />
            </div>
          </div>
          <div
            style={{
              display: 'flex',
              gap: 10,
              justifyContent: 'flex-end',
              marginTop: 18,
            }}
          >
            <button onClick={() => setModal(null)} style={CANCEL_BTN}>
              Cancelar
            </button>
            <button
              onClick={save}
              disabled={saving}
              style={{ ...SAVE_BTN, opacity: saving ? 0.7 : 1 }}
            >
              {saving ? 'Salvando...' : 'Salvar'}
            </button>
          </div>
        </Modal>
      )}
    </div>
  );
}

// ─── PAGAMENTOS ───────────────────────────────────────────────────────────────
function PagamentosTab() {
  const {
    data: pagamentos,
    loading,
    inserir,
    atualizar,
    deletar,
  } = useCRUD('pagamentos');
  const { data: projetos } = useCRUD('projetos', 'order=numero.asc');
  const { data: pedidos } = useCRUD('pedidos', 'order=numero.asc');
  const [modal, setModal] = useState(null);
  const [form, setForm] = useState({});
  const [saving, setSaving] = useState(false);
  const [search, setSearch] = useState('');
  const set = (k, v) => setForm((f) => ({ ...f, [k]: v }));

  // ao digitar nº do pedido, busca NF-e, projeto e valor automaticamente
  function handleNumeroPedido(valor) {
    const pedidoEncontrado = pedidos.find(
      (p) => String(p.numero) === String(valor.trim())
    );
    if (pedidoEncontrado) {
      const total = parseFloat(pedidoEncontrado.valor) || 0;
      setForm((f) => ({
        ...f,
        numero: valor,
        nfe: String(pedidoEncontrado.nfe || ''),
        projeto: String(pedidoEncontrado.projeto || f.projeto || ''),
        total: total,
        em_aberto: total,
        pago: parseFloat(f.pago) || 0,
        status_pgto: 'Não pago',
      }));
    } else {
      set('numero', valor);
    }
  }
  const tA = pagamentos.reduce((s, p) => s + (p.em_aberto || 0), 0);
  const tP = pagamentos.reduce((s, p) => s + (p.pago || 0), 0);
  const tG = pagamentos.reduce((s, p) => s + (p.total || 0), 0);
  const pct = (a, b) => (b ? Math.round((a / b) * 100) : 0);

  // busca por nº pedido, projeto, nf-e — ANTES do return condicional
  const pagFilt = useMemo(
    () =>
      pagamentos.filter((p) => {
        if (!search) return true;
        const q = search.toLowerCase();
        const pedVinc = pedidos.find(
          (ped) => String(ped.numero) === String(p.numero)
        );
        const nfe = (pedVinc?.nfe || p.nfe || '').toLowerCase();
        return (
          String(p.numero).toLowerCase().includes(q) ||
          String(p.projeto || '')
            .toLowerCase()
            .includes(q) ||
          nfe.includes(q)
        );
      }),
    [pagamentos, search, pedidos]
  );
  const [saveErro, setSaveErro] = useState('');
  async function save() {
    setSaving(true);
    setSaveErro('');
    const total = parseFloat(form.total) || 0;
    const pago = parseFloat(form.pago) || 0;
    const em_aberto = Math.max(total - pago, 0);
    const o = {
      ...form,
      total,
      pago,
      em_aberto,
      nfe: String(form.nfe || ''),
      numero: String(form.numero || ''),
      projeto: String(form.projeto || ''),
      condicao: String(form.condicao || ''),
      status_pgto: form.status_pgto || 'Não pago',
    };
    try {
      if (modal === 'new') await inserir({ ...o, id: uid() });
      else await atualizar(o.id, o);
      setModal(null);
    } finally {
      setSaving(false);
    }
  }
  async function del(id) {
    if (window.confirm('Excluir este pagamento?')) await deletar(id);
  }

  // calcula automaticamente em_aberto e status ao mudar total ou pago
  function calcular(field, value, currentForm) {
    const novoForm = { ...currentForm, [field]: value };
    const total =
      parseFloat(field === 'total' ? value : currentForm.total) || 0;
    const pago = parseFloat(field === 'pago' ? value : currentForm.pago) || 0;
    const emAberto = Math.max(total - pago, 0);
    let statusAuto = 'Não pago';
    if (pago > 0 && pago < total) statusAuto = 'Pago parcial';
    else if (pago >= total && total > 0) statusAuto = 'Pago total';
    return {
      ...novoForm,
      em_aberto: emAberto.toFixed(2),
      status_pgto: statusAuto,
    };
  }

  if (loading) return <Spin />;

  return (
    <div style={{ display: 'flex', flexDirection: 'column', gap: 14 }}>
      <div
        style={{
          display: 'grid',
          gridTemplateColumns: 'repeat(auto-fit,minmax(180px,1fr))',
          gap: 12,
        }}
      >
        <KPI icon="📋" label="Total Pedidos" value={fmt(tG)} color="#3B82F6" />
        <KPI
          icon="✅"
          label="Total Pago"
          value={fmt(tP)}
          color="#10B981"
          sub={`${pct(tP, tG)}% quitado`}
        />
        <KPI
          icon="⏳"
          label="Em Aberto"
          value={fmt(tA)}
          color="#EF4444"
          sub={`${pct(tA, tG)}% pendente`}
        />
      </div>
      <div
        style={{
          background: '#fff',
          borderRadius: 12,
          padding: '12px 16px',
          display: 'flex',
          gap: 10,
          alignItems: 'center',
          boxShadow: '0 1px 4px rgba(0,0,0,.06)',
        }}
      >
        <input
          value={search}
          onChange={(e) => setSearch(e.target.value)}
          placeholder="🔍 Buscar por Nº Pedido, Projeto ou NF-e..."
          style={{ ...INP, flex: 1 }}
        />
        {search && (
          <button
            onClick={() => setSearch('')}
            style={{
              padding: '7px 14px',
              border: '1.5px solid #E2E8F0',
              borderRadius: 8,
              background: 'none',
              color: '#64748B',
              fontWeight: 600,
              fontSize: 12,
              cursor: 'pointer',
              fontFamily: 'inherit',
              whiteSpace: 'nowrap',
            }}
          >
            ✕ Limpar
          </button>
        )}
        <span style={{ fontSize: 12, color: '#94A3B8', whiteSpace: 'nowrap' }}>
          {pagFilt.length} registro{pagFilt.length !== 1 ? 's' : ''}
        </span>
        <button
          onClick={() => {
            setForm({
              id: '',
              numero: '',
              projeto: '',
              nfe: '',
              status_pgto: 'Não pago',
              total: '',
              em_aberto: '',
              pago: '0',
              condicao: '',
            });
            setModal('new');
          }}
          style={{ ...SAVE_BTN, padding: '9px 20px', whiteSpace: 'nowrap' }}
        >
          + Novo Pagamento
        </button>
      </div>
      <div
        style={{
          background: '#fff',
          borderRadius: 14,
          boxShadow: '0 2px 8px rgba(0,0,0,.06)',
          overflow: 'hidden',
        }}
      >
        <table style={{ width: '100%', borderCollapse: 'collapse' }}>
          <thead>
            <tr>
              <TH>Ações</TH>
              <TH>Nº Pedido</TH>
              <TH>Projeto</TH>
              <TH>NF-e</TH>
              <TH>Status</TH>
              <TH>Total</TH>
              <TH>Em Aberto</TH>
              <TH>Pago</TH>
              <TH>% Pago</TH>
              <TH>Condição</TH>
            </tr>
          </thead>
          <tbody>
            {pagFilt.map((p, i) => {
              const pc = pct(p.pago, p.total);
              // busca NF-e sempre ao vivo do pedido correspondente
              const pedidoVinculado = pedidos.find(
                (ped) => String(ped.numero) === String(p.numero)
              );
              const nfeAtual = pedidoVinculado?.nfe || p.nfe || null;
              return (
                <tr
                  key={p.id}
                  style={{ background: i % 2 ? '#FAFBFC' : '#fff' }}
                  onMouseEnter={(e) =>
                    (e.currentTarget.style.background = '#EFF6FF')
                  }
                  onMouseLeave={(e) =>
                    (e.currentTarget.style.background =
                      i % 2 ? '#FAFBFC' : '#fff')
                  }
                >
                  <TD>
                    <div style={{ display: 'flex', gap: 5 }}>
                      <Btn
                        icon="✏️"
                        bg="#EFF6FF"
                        onClick={() => {
                          setForm({ ...p });
                          setModal('edit');
                        }}
                        title="Editar"
                      />
                      <Btn
                        icon="🗑️"
                        bg="#FEE2E2"
                        onClick={() => del(p.id)}
                        title="Excluir"
                      />
                    </div>
                  </TD>
                  <TD style={{ fontWeight: 800, color: '#8B5CF6' }}>
                    {p.numero}
                  </TD>
                  <TD style={{ fontWeight: 600, color: '#3B82F6' }}>
                    {p.projeto}
                  </TD>
                  <TD style={{ fontSize: 11 }}>
                    {nfeAtual ? (
                      <span
                        style={{
                          color: '#065F46',
                          fontWeight: 600,
                          background: '#D1FAE5',
                          padding: '2px 8px',
                          borderRadius: 8,
                        }}
                      >
                        {nfeAtual}
                      </span>
                    ) : (
                      <span style={{ color: '#94A3B8', fontStyle: 'italic' }}>
                        Aguardando faturamento
                      </span>
                    )}
                  </TD>
                  <TD>
                    <Badge s={p.status_pgto} />
                  </TD>
                  <TD style={{ fontWeight: 700 }}>{fmt(p.total)}</TD>
                  <TD
                    style={{
                      fontWeight: 700,
                      color: p.em_aberto > 0 ? '#EF4444' : '#10B981',
                    }}
                  >
                    {fmt(p.em_aberto)}
                  </TD>
                  <TD style={{ fontWeight: 700, color: '#10B981' }}>
                    {fmt(p.pago)}
                  </TD>
                  <TD>
                    <div
                      style={{ display: 'flex', alignItems: 'center', gap: 8 }}
                    >
                      <div
                        style={{
                          flex: 1,
                          background: '#F1F5F9',
                          borderRadius: 4,
                          height: 6,
                          minWidth: 50,
                        }}
                      >
                        <div
                          style={{
                            background:
                              pc === 100
                                ? '#10B981'
                                : pc > 0
                                ? '#F59E0B'
                                : '#EF4444',
                            borderRadius: 4,
                            height: 6,
                            width: `${pc}%`,
                          }}
                        />
                      </div>
                      <span style={{ fontSize: 11, fontWeight: 700 }}>
                        {pc}%
                      </span>
                    </div>
                  </TD>
                  <TD style={{ color: '#64748B', fontSize: 12 }}>
                    {p.condicao}
                  </TD>
                </tr>
              );
            })}
            {pagFilt.length === 0 && (
              <tr>
                <td
                  colSpan={10}
                  style={{ textAlign: 'center', padding: 40, color: '#94A3B8' }}
                >
                  {search
                    ? 'Nenhum resultado para esta busca'
                    : 'Nenhum pagamento cadastrado'}
                </td>
              </tr>
            )}
          </tbody>
        </table>
      </div>
      {modal && (
        <Modal
          title={modal === 'new' ? 'Novo Pagamento' : 'Editar Pagamento'}
          onClose={() => setModal(null)}
        >
          <div
            style={{ display: 'grid', gridTemplateColumns: '1fr 1fr', gap: 14 }}
          >
            <div>
              <label style={LBL}>Nº Pedido</label>
              <input
                style={INP}
                value={form.numero || ''}
                onChange={(e) => handleNumeroPedido(e.target.value)}
                placeholder="Digite o nº do pedido"
              />
              {form.numero &&
                pedidos.find(
                  (p) => String(p.numero) === String(form.numero)
                ) && (
                  <div
                    style={{
                      fontSize: 11,
                      color: '#10B981',
                      marginTop: 4,
                      fontWeight: 600,
                    }}
                  >
                    ✅ Pedido encontrado — dados preenchidos automaticamente!
                  </div>
                )}
              {form.numero &&
                !pedidos.find(
                  (p) => String(p.numero) === String(form.numero)
                ) &&
                String(form.numero).length > 2 && (
                  <div
                    style={{
                      fontSize: 11,
                      color: '#F59E0B',
                      marginTop: 4,
                      fontWeight: 600,
                    }}
                  >
                    ⚠️ Pedido não cadastrado — preencha manualmente
                  </div>
                )}
            </div>
            <div>
              <label style={LBL}>Projeto</label>
              <select
                style={INP}
                value={form.projeto || ''}
                onChange={(e) => set('projeto', e.target.value)}
              >
                <option value="">-- Selecione --</option>
                <option value="GERAIS">GERAIS</option>
                {projetos.map((p) => (
                  <option key={p.id} value={p.numero}>
                    {p.numero} — {p.nome} ({p.cliente})
                  </option>
                ))}
              </select>
              {form.projeto &&
                form.projeto !== 'GERAIS' &&
                projetos.find(
                  (p) => String(p.numero) === String(form.projeto)
                ) && (
                  <div
                    style={{
                      fontSize: 11,
                      color: '#3B82F6',
                      marginTop: 4,
                      fontWeight: 600,
                    }}
                  >
                    📁{' '}
                    {
                      projetos.find(
                        (p) => String(p.numero) === String(form.projeto)
                      )?.nome
                    }{' '}
                    ·{' '}
                    {
                      projetos.find(
                        (p) => String(p.numero) === String(form.projeto)
                      )?.cliente
                    }
                  </div>
                )}
            </div>
            <div style={{ gridColumn: 'span 2' }}>
              <label style={LBL}>NF-e (lida do pedido automaticamente)</label>
              {(() => {
                const ped = pedidos.find(
                  (p) => String(p.numero) === String(form.numero)
                );
                const nfe = ped?.nfe || null;
                return nfe ? (
                  <div
                    style={{
                      ...INP,
                      background: '#D1FAE5',
                      border: '1.5px solid #86EFAC',
                      color: '#065F46',
                      fontWeight: 700,
                    }}
                  >
                    {nfe}
                  </div>
                ) : (
                  <div
                    style={{
                      ...INP,
                      background: '#F8FAFC',
                      border: '1.5px solid #E2E8F0',
                      color: '#94A3B8',
                      fontStyle: 'italic',
                    }}
                  >
                    Aguardando faturamento — será preenchida ao cadastrar a NF
                    no pedido
                  </div>
                );
              })()}
            </div>
            <div>
              <label style={LBL}>Total do Pedido (R$)</label>
              <input
                style={INP}
                type="number"
                value={form.total || ''}
                onChange={(e) =>
                  setForm(calcular('total', e.target.value, form))
                }
                placeholder="0,00"
              />
            </div>
            <div>
              <label style={LBL}>Valor Pago (R$)</label>
              <input
                style={INP}
                type="number"
                value={form.pago || ''}
                onChange={(e) =>
                  setForm(calcular('pago', e.target.value, form))
                }
                placeholder="0,00"
              />
            </div>
            <div>
              <label style={LBL}>Em Aberto (R$) — calculado</label>
              <div
                style={{
                  ...INP,
                  background: '#F0FDF4',
                  border: '1.5px solid #86EFAC',
                  color: '#065F46',
                  fontWeight: 700,
                  display: 'flex',
                  alignItems: 'center',
                  justifyContent: 'space-between',
                }}
              >
                <span>
                  {form.total || form.pago
                    ? fmt(parseFloat(form.em_aberto) || 0)
                    : '—'}
                </span>
                <span
                  style={{ fontSize: 11, fontWeight: 700, color: '#10B981' }}
                >
                  auto
                </span>
              </div>
            </div>
            <div>
              <label style={LBL}>Status — calculado</label>
              <div
                style={{
                  ...INP,
                  background: '#F0FDF4',
                  border: '1.5px solid #86EFAC',
                  display: 'flex',
                  alignItems: 'center',
                }}
              >
                <Badge s={form.status_pgto || 'Não pago'} />
              </div>
            </div>
            <div style={{ gridColumn: 'span 2' }}>
              <label style={LBL}>Condição de Pagamento</label>
              <input
                style={INP}
                value={form.condicao || ''}
                onChange={(e) => set('condicao', e.target.value)}
                placeholder="Ex: 28ddl, 100% antecipado"
              />
            </div>
          </div>
          <div
            style={{
              fontSize: 11,
              color: '#64748B',
              marginTop: 4,
              padding: '8px 12px',
              background: '#F8FAFC',
              borderRadius: 8,
            }}
          >
            💡 Os campos <strong>Em Aberto</strong> e <strong>Status</strong>{' '}
            são calculados automaticamente conforme o valor pago.
          </div>
          <div
            style={{
              display: 'flex',
              gap: 10,
              justifyContent: 'flex-end',
              marginTop: 14,
            }}
          >
            <button onClick={() => setModal(null)} style={CANCEL_BTN}>
              Cancelar
            </button>
            <button
              onClick={save}
              disabled={saving}
              style={{ ...SAVE_BTN, opacity: saving ? 0.7 : 1 }}
            >
              {saving ? 'Salvando...' : 'Salvar'}
            </button>
          </div>
        </Modal>
      )}
    </div>
  );
}

// ─── DASHBOARD ────────────────────────────────────────────────────────────────
function Dashboard() {
  const { data: projetos, loading: lP } = useCRUD('projetos');
  const { data: pedidos, loading: lPed } = useCRUD('pedidos');
  const { data: pagamentos, loading: lPag } = useCRUD('pagamentos');
  const [filtro, setFiltro] = useState('todos');
  const hoje = new Date();

  // ── ALERTAS DO DIA — deve ficar ANTES de qualquer return condicional ──────
  const alertasHoje = useMemo(() => {
    const alertas = [];
    const hj = new Date();
    hj.setHours(0, 0, 0, 0);
    pedidos.forEach((p) => {
      if (p.status === 'Aguardando' && p.data_fatura) {
        const dt = parseLocal(p.data_fatura);
        if (dt && dt < hj)
          alertas.push({
            tipo: 'fat_atrasado',
            label: '⏰ Prazo faturamento',
            color: '#EF4444',
            bg: '#FEE2E2',
            pedido: p,
            detalhe: `Prazo: ${fmtDate(p.data_fatura)}`,
          });
      }
      // 2. Atraso prazo de entrega — só para Faturado Inicial (ainda não entregue)
      if (p.status === 'Faturado Inicial' && p.data_entrega) {
        const dt = parseLocal(p.data_entrega);
        if (dt && dt < hj)
          alertas.push({
            tipo: 'ent_atrasado',
            label: '🚚 Atraso na entrega',
            color: '#8B5CF6',
            bg: '#EDE9FE',
            pedido: p,
            detalhe: `Prazo: ${fmtDate(p.data_entrega)}`,
          });
      }
      if (p.itens_pendentes) {
        let itens = [];
        try {
          itens = JSON.parse(p.itens_pendentes);
        } catch {}
        itens.forEach((it) => {
          if (!it.faturado && it.prazoPrev) {
            const dt = parseLocal(it.prazoPrev);
            if (dt && dt < hj)
              alertas.push({
                tipo: 'item_atrasado',
                label: '📦 Item pendente',
                color: '#F97316',
                bg: '#FFF7ED',
                pedido: p,
                detalhe: `${it.codigo} x${it.quantidade} — Prev: ${fmtDate(
                  it.prazoPrev
                )}`,
              });
          }
        });
      }
    });
    return alertas;
  }, [pedidos]);

  if (lP || lPed || lPag) return <Spin />;

  const hojeDash = new Date();
  hojeDash.setHours(0, 0, 0, 0);
  const temItensEmAtraso = (p) => {
    if (!p.itens_pendentes) return false;
    try {
      const itens = JSON.parse(p.itens_pendentes);
      return itens.some((it) => !it.faturado);
    } catch {
      return false;
    }
  };
  const getMotivo = (p) => {
    if (p.status === 'Aguardando') return 'nao_faturou';
    if (p.status === 'Entregue Parcial') return 'entregue_parcial';
    if (p.obs && p.obs.toLowerCase().includes('faturamento previsto'))
      return 'fat_previsto';
    return 'outros';
  };
  // "Entregue Parcial" só entra no follow-up se tiver itens pendentes ainda não faturados
  const pendencias = pedidos.filter((p) => {
    if (p.status === 'Aguardando') return true;
    if (p.status === 'Entregue Parcial') return temItensEmAtraso(p);
    if (p.obs && p.obs.toLowerCase().includes('faturamento previsto'))
      return true;
    return false;
  });
  const counts = {
    todos: pendencias.length,
    nao_faturou: pendencias.filter((p) => getMotivo(p) === 'nao_faturou')
      .length,
    entregue_parcial: pendencias.filter(
      (p) => getMotivo(p) === 'entregue_parcial'
    ).length,
    fat_previsto: pendencias.filter((p) => getMotivo(p) === 'fat_previsto')
      .length,
  };
  const filtrados = pendencias.filter(
    (p) => filtro === 'todos' || getMotivo(p) === filtro
  );
  const MC = {
    nao_faturou: { label: '🔴 Não faturou', color: '#EF4444' },
    entregue_parcial: { label: '🟣 Entregue Parcial', color: '#8B5CF6' },
    fat_previsto: { label: '🟠 Fat. previsto', color: '#F97316' },
    outros: { label: 'Outro', color: '#64748B' },
  };
  const tAberto = pagamentos.reduce((s, p) => s + (p.em_aberto || 0), 0);
  const tPago = pagamentos.reduce((s, p) => s + (p.pago || 0), 0);
  const porCliente = Object.entries(
    projetos.reduce((acc, p) => {
      acc[p.cliente] = (acc[p.cliente] || 0) + p.valor;
      return acc;
    }, {})
  )
    .sort((a, b) => b[1] - a[1])
    .slice(0, 5);
  const maxV = Math.max(...porCliente.map((x) => x[1]), 1);
  return (
    <div style={{ display: 'flex', flexDirection: 'column', gap: 18 }}>
      <div
        style={{
          display: 'grid',
          gridTemplateColumns: 'repeat(auto-fit,minmax(160px,1fr))',
          gap: 12,
        }}
      >
        <KPI
          icon="📁"
          label="Projetos Ativos"
          value={projetos.filter((p) => p.status === 'NÃO ENTREGUE').length}
          sub={`${
            projetos.filter((p) => p.status === 'ENTREGUE').length
          } entregues`}
          color="#3B82F6"
        />
        <KPI
          icon="💰"
          label="Valor Total"
          value={fmt(projetos.reduce((s, p) => s + p.valor, 0))}
          color="#8B5CF6"
        />
        <KPI
          icon="📦"
          label="Pedidos"
          value={pedidos.length}
          sub={`${
            pedidos.filter((p) => p.status === 'Aguardando').length
          } aguardando`}
          color="#F59E0B"
        />
        <KPI
          icon="🚨"
          label="Pendências"
          value={pendencias.length}
          color="#EF4444"
        />
        <KPI icon="💳" label="Em Aberto" value={fmt(tAberto)} color="#EF4444" />
        <KPI icon="✅" label="Já Pago" value={fmt(tPago)} color="#10B981" />
      </div>
      <div style={{ display: 'grid', gridTemplateColumns: '1fr 1fr', gap: 16 }}>
        <div
          style={{
            background: '#fff',
            borderRadius: 14,
            padding: 22,
            boxShadow: '0 2px 8px rgba(0,0,0,.06)',
          }}
        >
          <div style={{ fontWeight: 800, fontSize: 14, marginBottom: 16 }}>
            💼 Valor por Cliente
          </div>
          {porCliente.map(([cli, val]) => (
            <div key={cli} style={{ marginBottom: 12 }}>
              <div
                style={{
                  display: 'flex',
                  justifyContent: 'space-between',
                  marginBottom: 4,
                }}
              >
                <span style={{ fontSize: 12, fontWeight: 500 }}>{cli}</span>
                <span
                  style={{ fontSize: 12, fontWeight: 700, color: '#3B82F6' }}
                >
                  {fmt(val)}
                </span>
              </div>
              <div
                style={{ background: '#F1F5F9', borderRadius: 6, height: 8 }}
              >
                <div
                  style={{
                    background: '#3B82F6',
                    borderRadius: 6,
                    height: 8,
                    width: `${(val / maxV) * 100}%`,
                  }}
                />
              </div>
            </div>
          ))}
          {porCliente.length === 0 && (
            <div style={{ textAlign: 'center', color: '#94A3B8', padding: 20 }}>
              Nenhum projeto cadastrado
            </div>
          )}
        </div>
        <div
          style={{
            background: '#fff',
            borderRadius: 14,
            padding: 22,
            boxShadow: '0 2px 8px rgba(0,0,0,.06)',
          }}
        >
          <div style={{ fontWeight: 800, fontSize: 14, marginBottom: 16 }}>
            📊 Pedidos por Status
          </div>
          {[
            'Concluído',
            'Aguardando',
            'Faturado Inicial',
            'Entregue Parcial',
          ].map((s) => {
            const c = SC[s] || { dot: '#64748B' };
            const cnt = pedidos.filter((p) => p.status === s).length;
            return (
              <div key={s} style={{ marginBottom: 12 }}>
                <div
                  style={{
                    display: 'flex',
                    justifyContent: 'space-between',
                    marginBottom: 4,
                  }}
                >
                  <span style={{ fontSize: 12, fontWeight: 500 }}>{s}</span>
                  <span style={{ fontSize: 12, fontWeight: 700, color: c.dot }}>
                    {cnt}
                  </span>
                </div>
                <div
                  style={{ background: '#F1F5F9', borderRadius: 6, height: 8 }}
                >
                  <div
                    style={{
                      background: c.dot,
                      borderRadius: 6,
                      height: 8,
                      width: pedidos.length
                        ? `${(cnt / pedidos.length) * 100}%`
                        : '0%',
                    }}
                  />
                </div>
              </div>
            );
          })}
        </div>
      </div>
      {/* ALERTAS DO DIA */}
      <div
        style={{
          background: '#fff',
          borderRadius: 14,
          boxShadow: '0 2px 8px rgba(0,0,0,.06)',
          overflow: 'hidden',
        }}
      >
        <div
          style={{
            padding: '14px 20px',
            borderBottom: '1px solid #F1F5F9',
            display: 'flex',
            alignItems: 'center',
            justifyContent: 'space-between',
            flexWrap: 'wrap',
            gap: 10,
          }}
        >
          <div style={{ display: 'flex', alignItems: 'center', gap: 10 }}>
            <div style={{ fontWeight: 800, fontSize: 14, color: '#0F172A' }}>
              🔔 Alertas do Dia —{' '}
              {new Date().toLocaleDateString('pt-BR', {
                weekday: 'long',
                day: '2-digit',
                month: 'long',
              })}
            </div>
            <span
              style={{
                fontSize: 12,
                fontWeight: 700,
                background: alertasHoje.length > 0 ? '#FEE2E2' : '#D1FAE5',
                color: alertasHoje.length > 0 ? '#991B1B' : '#065F46',
                padding: '3px 12px',
                borderRadius: 20,
              }}
            >
              {alertasHoje.length} alerta{alertasHoje.length !== 1 ? 's' : ''}
            </span>
          </div>
          {alertasHoje.length > 0 && (
            <div style={{ display: 'flex', gap: 8 }}>
              {/* XLS */}
              <button
                onClick={() => {
                  const dataHoje = new Date().toLocaleDateString('pt-BR');
                  const html = `<html xmlns:o="urn:schemas-microsoft-com:office:office" xmlns:x="urn:schemas-microsoft-com:office:excel"><head><meta charset="UTF-8"><style>body{font-family:Calibri,Arial;font-size:11pt;}.header{background:#0A0F1E;color:#fff;font-size:14pt;font-weight:bold;padding:10px;}.subheader{background:#00BCD4;color:#fff;font-size:10pt;padding:6px;}th{background:#0F172A;color:#fff;font-weight:bold;font-size:10pt;padding:8px;border:1px solid #334155;text-align:left;}td{font-size:10pt;padding:6px 8px;border:1px solid #E2E8F0;vertical-align:top;}tr:nth-child(even) td{background:#F0FDFF;}tr:nth-child(odd) td{background:#FFF;}.total-row td{background:#0F172A;color:#fff;font-weight:bold;border:1px solid #334155;}</style></head><body><table><tr><td colspan="5" class="header">ZETTATECCK PROJETOS — Alertas do Dia</td></tr><tr><td colspan="5" class="subheader">Sistema de Gestão de Compras · ${dataHoje}</td></tr><tr><td colspan="5" style="padding:4px;"></td></tr><tr><th>Tipo</th><th>Nº Pedido</th><th>Fornecedor</th><th>Projeto</th><th>Detalhe</th></tr>${alertasHoje
                    .map(
                      (a) =>
                        `<tr><td>${a.label}</td><td>${
                          a.pedido.numero
                        }</td><td>${a.pedido.fornecedor}</td><td>${
                          a.pedido.projeto || 'GERAIS'
                        }</td><td>${a.detalhe}</td></tr>`
                    )
                    .join('')}<tr class="total-row"><td colspan="5">Total: ${
                    alertasHoje.length
                  } alerta(s) · Zettatecck Projetos · ${dataHoje}</td></tr></table></body></html>`;
                  const blob = new Blob([html], {
                    type: 'application/vnd.ms-excel;charset=utf-8',
                  });
                  const a = document.createElement('a');
                  a.href = URL.createObjectURL(blob);
                  a.download = `alertas-dia-${
                    new Date().toISOString().split('T')[0]
                  }.xls`;
                  a.click();
                }}
                style={{
                  padding: '7px 14px',
                  background: '#F0FDF4',
                  border: '2px solid #10B981',
                  borderRadius: 8,
                  color: '#065F46',
                  fontWeight: 700,
                  fontSize: 12,
                  cursor: 'pointer',
                  fontFamily: 'inherit',
                  display: 'flex',
                  alignItems: 'center',
                  gap: 6,
                }}
              >
                📥 Excel
              </button>
              {/* PDF */}
              <button
                onClick={() => {
                  const dataHoje = new Date().toLocaleString('pt-BR');
                  const corMap = {
                    fat_atrasado: '#EF4444',
                    ent_atrasado: '#8B5CF6',
                    item_atrasado: '#F97316',
                  };
                  const bgMap = {
                    fat_atrasado: '#FEE2E2',
                    ent_atrasado: '#EDE9FE',
                    item_atrasado: '#FFF7ED',
                  };
                  const html = `<!DOCTYPE html><html><head><meta charset="utf-8"><title>Alertas do Dia</title><style>*{box-sizing:border-box;margin:0;padding:0;}body{font-family:Arial,sans-serif;font-size:10px;color:#1E293B;}.header{background:linear-gradient(135deg,#0A0F1E,#0F3460);color:#fff;padding:20px 28px;display:flex;align-items:center;justify-content:space-between;}.logo-img{width:48px;height:48px;border-radius:10px;object-fit:cover;}.company{color:#fff;font-size:16px;font-weight:900;}.company-sub{color:#22D3EE;font-size:9px;font-weight:600;text-transform:uppercase;letter-spacing:1px;margin-top:2px;}.meta-bar{background:#00BCD4;color:#0A0F1E;padding:8px 28px;font-size:9px;font-weight:700;display:flex;justify-content:space-between;}.content{padding:20px 28px;}.alerta{display:flex;align-items:center;gap:12px;padding:10px 14px;border-radius:8px;margin-bottom:8px;font-size:10px;}.footer{background:#F8FAFC;border-top:2px solid #00BCD4;padding:10px 28px;display:flex;justify-content:space-between;font-size:8px;color:#64748B;margin-top:20px;}@media print{body{-webkit-print-color-adjust:exact;print-color-adjust:exact;}}</style></head><body><div class="header"><div style="display:flex;align-items:center;gap:16px;"><img src="${LOGO}" class="logo-img" alt="Z"/><div><div class="company">Zettatecck Projetos</div><div class="company-sub">Sistema de Gestão de Compras</div></div></div><div style="text-align:right;"><div style="color:#fff;font-size:13px;font-weight:700;">🔔 Alertas do Dia</div><div style="color:#94A3B8;font-size:9px;margin-top:3px;">${dataHoje}</div></div></div><div class="meta-bar"><span>Total de alertas: <strong>${
                    alertasHoje.length
                  }</strong></span><span>${new Date().toLocaleDateString(
                    'pt-BR',
                    {
                      weekday: 'long',
                      day: '2-digit',
                      month: 'long',
                      year: 'numeric',
                    }
                  )}</span></div><div class="content">${alertasHoje
                    .map(
                      (a) =>
                        `<div class="alerta" style="background:${
                          bgMap[a.tipo] || '#F8FAFC'
                        };border:1px solid ${
                          corMap[a.tipo] || '#E2E8F0'
                        }30;"><span style="font-weight:800;color:${
                          corMap[a.tipo] || '#374151'
                        };min-width:160px;">${
                          a.label
                        }</span><span style="font-weight:700;color:#8B5CF6;min-width:60px;">#${
                          a.pedido.numero
                        }</span><span style="font-weight:600;color:#374151;flex:1;">${
                          a.pedido.fornecedor
                        }</span><span style="color:#64748B;min-width:80px;">${
                          a.pedido.projeto || 'GERAIS'
                        }</span><span style="font-weight:700;color:${
                          corMap[a.tipo] || '#374151'
                        };">${a.detalhe}</span></div>`
                    )
                    .join(
                      ''
                    )}</div><div class="footer"><span><strong>Zettatecck Projetos</strong> — Sistema de Gestão de Compras</span><span>${
                    alertasHoje.length
                  } alerta(s) · ${dataHoje}</span></div></body></html>`;
                  const w = window.open('', '_blank');
                  if (!w) {
                    alert('Permita pop-ups para exportar o PDF.');
                    return;
                  }
                  w.document.write(html);
                  w.document.close();
                  w.onload = () => {
                    setTimeout(() => w.print(), 300);
                  };
                }}
                style={{
                  padding: '7px 14px',
                  background: '#EFF6FF',
                  border: '2px solid #3B82F6',
                  borderRadius: 8,
                  color: '#1E40AF',
                  fontWeight: 700,
                  fontSize: 12,
                  cursor: 'pointer',
                  fontFamily: 'inherit',
                  display: 'flex',
                  alignItems: 'center',
                  gap: 6,
                }}
              >
                🖨️ PDF
              </button>
              {/* E-MAIL */}
              <button
                onClick={() => {
                  const dataStr = new Date().toLocaleDateString('pt-BR', {
                    weekday: 'long',
                    day: '2-digit',
                    month: 'long',
                    year: 'numeric',
                  });
                  const assunto = encodeURIComponent(
                    `🔔 Alertas do Dia — ${new Date().toLocaleDateString(
                      'pt-BR'
                    )} — Zettatecck Projetos`
                  );
                  const linhas = alertasHoje
                    .map(
                      (a) =>
                        `• ${a.label.replace(
                          /[^\w\s\-\.\/ç]/g,
                          ''
                        )} | Pedido #${a.pedido.numero} | ${
                          a.pedido.fornecedor
                        } | Projeto: ${a.pedido.projeto || 'GERAIS'} | ${
                          a.detalhe
                        }`
                    )
                    .join('\n');
                  const corpo = encodeURIComponent(
                    `Olá,\n\nSegue o resumo dos alertas do dia ${dataStr}:\n\n${linhas}\n\nTotal: ${alertasHoje.length} alerta(s)\n\nAtenciosamente,\nZettatecck Projetos — Sistema de Gestão de Compras`
                  );
                  window.location.href = `mailto:?subject=${assunto}&body=${corpo}`;
                }}
                style={{
                  padding: '7px 14px',
                  background: '#F0FDF4',
                  border: '2px solid #8B5CF6',
                  borderRadius: 8,
                  color: '#5B21B6',
                  fontWeight: 700,
                  fontSize: 12,
                  cursor: 'pointer',
                  fontFamily: 'inherit',
                  display: 'flex',
                  alignItems: 'center',
                  gap: 6,
                }}
              >
                📧 E-mail
              </button>
            </div>
          )}
        </div>
        {alertasHoje.length === 0 ? (
          <div
            style={{
              padding: 28,
              textAlign: 'center',
              color: '#10B981',
              fontWeight: 700,
              fontSize: 14,
            }}
          >
            ✅ Nenhum alerta para hoje! Tudo em dia.
          </div>
        ) : (
          <div
            style={{
              padding: '12px 16px',
              display: 'flex',
              flexDirection: 'column',
              gap: 8,
            }}
          >
            {alertasHoje.map((a, i) => (
              <div
                key={i}
                style={{
                  display: 'flex',
                  alignItems: 'center',
                  gap: 12,
                  padding: '10px 14px',
                  borderRadius: 10,
                  background: a.bg,
                  border: `1px solid ${a.color}30`,
                  flexWrap: 'wrap',
                }}
              >
                <span
                  style={{
                    fontSize: 12,
                    fontWeight: 800,
                    color: a.color,
                    whiteSpace: 'nowrap',
                  }}
                >
                  {a.label}
                </span>
                <span
                  style={{
                    fontSize: 12,
                    fontWeight: 700,
                    color: '#8B5CF6',
                    flexShrink: 0,
                  }}
                >
                  #{a.pedido.numero}
                </span>
                <span
                  style={{
                    fontSize: 12,
                    color: '#374151',
                    fontWeight: 600,
                    flex: 1,
                    minWidth: 100,
                  }}
                >
                  {a.pedido.fornecedor}
                </span>
                <span style={{ fontSize: 12, color: '#64748B', flexShrink: 0 }}>
                  {a.pedido.projeto || 'GERAIS'}
                </span>
                <span
                  style={{
                    fontSize: 11,
                    fontWeight: 700,
                    color: a.color,
                    whiteSpace: 'nowrap',
                  }}
                >
                  {a.detalhe}
                </span>
              </div>
            ))}
          </div>
        )}
      </div>

      <div
        style={{
          background: '#fff',
          borderRadius: 14,
          boxShadow: '0 2px 8px rgba(0,0,0,.06)',
          overflow: 'hidden',
        }}
      >
        <div
          style={{
            padding: '14px 20px',
            borderBottom: '1px solid #F1F5F9',
            display: 'flex',
            alignItems: 'center',
            justifyContent: 'space-between',
            flexWrap: 'wrap',
            gap: 10,
          }}
        >
          <div style={{ fontWeight: 800, fontSize: 14 }}>
            🚨 Follow-up de Pendências ({pendencias.length})
          </div>
          <div style={{ display: 'flex', gap: 8, flexWrap: 'wrap' }}>
            {[
              ['todos', `Todos (${counts.todos})`],
              ['nao_faturou', `Não Faturou (${counts.nao_faturou})`],
              ['entregue_parcial', `Parcial (${counts.entregue_parcial})`],
              ['fat_previsto', `Fat. Previsto (${counts.fat_previsto})`],
            ].map(([k, l]) => (
              <button
                key={k}
                onClick={() => setFiltro(k)}
                style={{
                  padding: '5px 12px',
                  border: 'none',
                  borderRadius: 20,
                  cursor: 'pointer',
                  fontSize: 12,
                  fontWeight: 700,
                  fontFamily: 'inherit',
                  background: filtro === k ? '#0F172A' : '#F1F5F9',
                  color: filtro === k ? '#fff' : '#64748B',
                }}
              >
                {l}
              </button>
            ))}
          </div>
        </div>
        <div style={{ overflowX: 'auto' }}>
          <table style={{ width: '100%', borderCollapse: 'collapse' }}>
            <thead>
              <tr>
                <TH>Tipo</TH>
                <TH>Nº</TH>
                <TH>Fornecedor</TH>
                <TH>Projeto</TH>
                <TH>Valor</TH>
                <TH>Status</TH>
                <TH>Prazo Entrega</TH>
                <TH>Observação</TH>
              </tr>
            </thead>
            <tbody>
              {filtrados.length === 0 && (
                <tr>
                  <td
                    colSpan={8}
                    style={{
                      textAlign: 'center',
                      padding: 40,
                      color: '#94A3B8',
                    }}
                  >
                    Nenhuma pendência neste filtro 🎉
                  </td>
                </tr>
              )}
              {filtrados.map((p, i) => {
                const m = getMotivo(p);
                const mc = MC[m] || MC.outros;
                return (
                  <tr
                    key={p.id}
                    style={{ background: i % 2 ? '#FAFBFC' : '#fff' }}
                  >
                    <TD>
                      <span
                        style={{
                          fontSize: 11,
                          fontWeight: 700,
                          color: mc.color,
                          background: `${mc.color}18`,
                          padding: '3px 9px',
                          borderRadius: 12,
                          whiteSpace: 'nowrap',
                        }}
                      >
                        {mc.label}
                      </span>
                    </TD>
                    <TD style={{ fontWeight: 800, color: '#8B5CF6' }}>
                      {p.numero}
                    </TD>
                    <TD style={{ fontWeight: 600 }}>{p.fornecedor}</TD>
                    <TD style={{ fontWeight: 600, color: '#3B82F6' }}>
                      {p.projeto || 'GERAIS'}
                    </TD>
                    <TD style={{ fontWeight: 700 }}>{fmt(p.valor)}</TD>
                    <TD>
                      <Badge s={p.status} />
                    </TD>
                    <TD
                      style={{
                        whiteSpace: 'nowrap',
                        color: (() => {
                          if (
                            p.status === 'Concluído' ||
                            p.status === 'Entregue Parcial'
                          )
                            return '#10B981'; // já entregue, data real = verde
                          return p.data_entrega &&
                            parseLocal(p.data_entrega) < hoje
                            ? '#EF4444'
                            : '#374151'; // prazo: vermelho se venceu
                        })(),
                        fontWeight:
                          p.status !== 'Concluído' &&
                          p.status !== 'Entregue Parcial' &&
                          p.data_entrega &&
                          parseLocal(p.data_entrega) < hoje
                            ? 700
                            : 400,
                      }}
                    >
                      {fmtDate(p.data_entrega)}
                    </TD>
                    <TD
                      style={{ maxWidth: 200, color: '#64748B', fontSize: 11 }}
                    >
                      {p.obs}
                    </TD>
                  </tr>
                );
              })}
            </tbody>
          </table>
        </div>
      </div>
    </div>
  );
}

// ─── RELATÓRIO ────────────────────────────────────────────────────────────────
function RelatorioTab() {
  const { data: projetos } = useCRUD('projetos');
  const { data: pedidos } = useCRUD('pedidos');
  const { data: pagamentos } = useCRUD('pagamentos');
  const { data: fornecedores } = useCRUD('fornecedores');
  const [step, setStep] = useState(1);
  const [tipo, setTipo] = useState('pedidos');
  const [cols, setCols] = useState({});
  const [filtros, setFiltros] = useState({
    status: 'all',
    pendencia: 'all',
    anos: [],
  });

  // anos disponíveis extraídos dos pedidos cadastrados
  const anosDisponiveis = useMemo(() => {
    const set = new Set();
    pedidos.forEach((p) => {
      if (p.data_fatura) {
        const a = p.data_fatura.split('-')[0];
        if (a) set.add(a);
      }
      if (p.data_entrega) {
        const a = p.data_entrega.split('-')[0];
        if (a) set.add(a);
      }
    });
    return Array.from(set).sort((a, b) => b - a);
  }, [pedidos]);
  const COLS = {
    pedidos: [
      'Nº Pedido',
      'Fornecedor',
      'Projeto',
      'Valor',
      'Status',
      'NF-e',
      'Prazo Fatura',
      'Prazo Entrega',
      'Pendência',
      'Itens Pendentes',
      'Observação',
    ],
    projetos: [
      'Número',
      'Nome',
      'Cliente',
      'Cidade',
      'Valor',
      'Máx Compras',
      'Previsão Entrega',
      'Status',
    ],
    pagamentos: [
      'Nº Pedido',
      'Projeto',
      'NF-e',
      'Status Pgto',
      'Total',
      'Em Aberto',
      'Pago',
      'Condição',
    ],
    fornecedores: ['Empresa', 'Responsável', 'Telefone', 'E-mail'],
  };
  const selCols = COLS[tipo].filter((c) => cols[c]);
  function toggleCol(c) {
    setCols((p) => ({ ...p, [c]: !p[c] }));
  }
  function selAll() {
    const o = {};
    COLS[tipo].forEach((c) => (o[c] = true));
    setCols(o);
  }
  function getData() {
    if (tipo === 'pedidos') {
      const hoje = new Date();
      hoje.setHours(0, 0, 0, 0);
      let d = pedidos;
      if (filtros.status !== 'all')
        d = d.filter((p) => p.status === filtros.status);
      if (filtros.pendencia !== 'all')
        d = d.filter((p) => p.pendencia === filtros.pendencia);
      if (filtros.anos && filtros.anos.length > 0) {
        d = d.filter((p) => {
          const anoFat = p.data_fatura ? p.data_fatura.split('-')[0] : null;
          const anoEnt = p.data_entrega ? p.data_entrega.split('-')[0] : null;
          return filtros.anos.includes(anoFat) || filtros.anos.includes(anoEnt);
        });
      }
      return d.map((p) => {
        const itens = p.itens_pendentes ? JSON.parse(p.itens_pendentes) : [];
        const itensTexto =
          itens.length === 0
            ? '—'
            : itens
                .map((it) => {
                  const prazo = it.prazoPrev ? parseLocal(it.prazoPrev) : null;
                  const status = it.faturado
                    ? `FATURADO em ${fmtDate(it.dataFaturamento)}`
                    : it.emAtraso
                    ? 'EM ATRASO (CONF. NOVA DATA)'
                    : prazo && prazo < hoje
                    ? 'EM ATRASO'
                    : it.prazoPrev
                    ? `prev. ${fmtDate(it.prazoPrev)}`
                    : 'pendente';
                  return `${it.codigo} x${it.quantidade} [${status}]`;
                })
                .join(' | ');
        return {
          'Nº Pedido': p.numero,
          Fornecedor: p.fornecedor,
          Projeto: p.projeto || 'GERAIS',
          Valor: fmt(p.valor),
          Status: p.status,
          'NF-e': p.nfe || '—',
          'Prazo Fatura': fmtDate(p.data_fatura),
          'Prazo Entrega': fmtDate(p.data_entrega),
          Pendência: p.pendencia,
          'Itens Pendentes': itensTexto,
          Observação: p.obs,
        };
      });
    }
    if (tipo === 'projetos')
      return projetos.map((p) => ({
        Número: p.numero,
        Nome: p.nome,
        Cliente: p.cliente,
        Cidade: p.cidade,
        Valor: fmt(p.valor),
        'Máx Compras': fmt(p.max_compras),
        'Previsão Entrega': fmtDate(p.previsao_entrega),
        Status: p.status,
      }));
    if (tipo === 'pagamentos')
      return pagamentos.map((p) => ({
        'Nº Pedido': p.numero,
        Projeto: p.projeto,
        'NF-e': p.nfe || '—',
        'Status Pgto': p.status_pgto,
        Total: fmt(p.total),
        'Em Aberto': fmt(p.em_aberto),
        Pago: fmt(p.pago),
        Condição: p.condicao,
      }));
    return fornecedores.map((f) => ({
      Empresa: f.nome,
      Responsável: f.responsavel,
      Telefone: f.telefone,
      'E-mail': f.email,
      Categoria: f.categoria,
    }));
  }
  // helper: renderiza itens pendentes como HTML colorido para XLS e PDF
  function itensHtml(itensJson, pendencia) {
    if (!itensJson) {
      return pendencia === 'Sim'
        ? `<span style="background:#D1FAE5;color:#065F46;border-radius:5px;padding:3px 8px;font-size:10px;font-weight:700;">✅ Pendência(s) entregue(s)</span>`
        : '—';
    }
    let itens = [];
    try {
      itens = JSON.parse(itensJson);
    } catch {
      return '—';
    }
    if (!itens.length) {
      return pendencia === 'Sim'
        ? `<span style="background:#D1FAE5;color:#065F46;border-radius:5px;padding:3px 8px;font-size:10px;font-weight:700;">✅ Pendência(s) entregue(s)</span>`
        : '—';
    }
    const hoje = new Date();
    hoje.setHours(0, 0, 0, 0);
    const rows = itens
      .map((it) => {
        const prazo = it.prazoPrev ? parseLocal(it.prazoPrev) : null;
        const vencido = !it.faturado && !it.emAtraso && prazo && prazo < hoje;
        const bg = it.faturado
          ? '#D1FAE5'
          : it.emAtraso
          ? '#FEE2E2'
          : vencido
          ? '#FEE2E2'
          : '#FEF3C7';
        const color = it.faturado
          ? '#065F46'
          : it.emAtraso
          ? '#991B1B'
          : vencido
          ? '#991B1B'
          : '#92400E';
        const label = it.faturado
          ? `✓ Fat. ${fmtDate(it.dataFaturamento)}`
          : it.emAtraso
          ? '🔴 Conf. nova data'
          : vencido
          ? '🔴 Em atraso'
          : `⏳ Prev. ${it.prazoPrev ? fmtDate(it.prazoPrev) : 's/prazo'}`;
        return `<div style="display:flex;align-items:center;gap:8px;background:${bg};border-radius:5px;padding:4px 8px;margin-bottom:3px;"><span style="color:${color};font-size:11px;font-weight:700;flex:1;">${it.codigo}</span><span style="color:${color};font-size:11px;">x${it.quantidade}</span><span style="color:${color};font-size:11px;font-weight:700;">${label}</span></div>`;
      })
      .join('');
    const todosEntregues = itens.every((it) => it.faturado);
    const sufixo =
      todosEntregues && pendencia === 'Sim'
        ? `<div style="color:#10B981;font-size:11px;font-weight:700;margin-top:4px;">✅ Pendência(s) entregue(s)</div>`
        : '';
    return rows + sufixo;
  }

  function exportXLS() {
    const rawData =
      tipo === 'pedidos'
        ? (() => {
            const hoje = new Date();
            hoje.setHours(0, 0, 0, 0);
            let d = pedidos;
            if (filtros.status !== 'all')
              d = d.filter((p) => p.status === filtros.status);
            if (filtros.pendencia !== 'all')
              d = d.filter((p) => p.pendencia === filtros.pendencia);
            if (filtros.anos && filtros.anos.length > 0) {
              d = d.filter((p) => {
                const af = p.data_fatura ? p.data_fatura.split('-')[0] : null;
                const ae = p.data_entrega ? p.data_entrega.split('-')[0] : null;
                return filtros.anos.includes(af) || filtros.anos.includes(ae);
              });
            }
            return d.map((p) => ({
              ...p,
              _itensHtml: itensHtml(p.itens_pendentes, p.pendencia),
            }));
          })()
        : null;

    const data = getData();
    const tipoLabel = {
      pedidos: 'Pedidos de Compra',
      projetos: 'Projetos',
      pagamentos: 'Pagamentos',
      fornecedores: 'Fornecedores',
    }[tipo];
    const dataHoje = new Date().toLocaleDateString('pt-BR');

    const buildCell = (col, row, idx) => {
      if (col === 'Itens Pendentes' && rawData) {
        return `<td>${rawData[idx]?._itensHtml || '—'}</td>`;
      }
      return `<td>${row[col] || '—'}</td>`;
    };

    const html = `<html xmlns:o="urn:schemas-microsoft-com:office:office" xmlns:x="urn:schemas-microsoft-com:office:excel">
<head><meta charset="UTF-8">
<style>
  body{font-family:Calibri,Arial;font-size:11pt;}
  .header{background:#0A0F1E;color:#fff;font-size:14pt;font-weight:bold;padding:10px;}
  .subheader{background:#00BCD4;color:#fff;font-size:10pt;padding:6px;}
  .meta{color:#64748B;font-size:9pt;padding:4px;}
  th{background:#0F172A;color:#ffffff;font-weight:bold;font-size:10pt;padding:8px;border:1px solid #334155;text-align:left;}
  td{font-size:10pt;padding:6px 8px;border:1px solid #E2E8F0;vertical-align:top;}
  td.itens-col{width:392px;font-size:9pt;}
  td.itens-col div{font-size:9pt !important;}
  td.itens-col span{font-size:9pt !important;}
  tr:nth-child(even) td{background:#F0FDFF;}
  tr:nth-child(odd) td{background:#FFFFFF;}
  .total-row td{background:#0F172A;color:#fff;font-weight:bold;border:1px solid #334155;}
</style></head><body>
<table>
  <tr><td colspan="${
    selCols.length
  }" class="header">ZETTATECCK PROJETOS — Relatório de ${tipoLabel}</td></tr>
  <tr><td colspan="${
    selCols.length
  }" class="subheader">Sistema de Gestão de Compras · Gerado em ${dataHoje}</td></tr>
  <tr><td colspan="${selCols.length}" class="meta">Total de registros: ${
      data.length
    }</td></tr>
  <tr><td colspan="${selCols.length}" style="padding:4px;"></td></tr>
  <tr>${selCols.map((c) => `<th>${c}</th>`).join('')}</tr>
  ${data
    .map(
      (r, i) =>
        `<tr>${selCols
          .map((c) =>
            c === 'Itens Pendentes'
              ? `<td class="itens-col">${rawData?.[i]?._itensHtml || '—'}</td>`
              : `<td>${r[c] || '—'}</td>`
          )
          .join('')}</tr>`
    )
    .join('')}
  <tr class="total-row"><td colspan="${selCols.length}">Total de ${
      data.length
    } registro(s) · Zettatecck Projetos · ${dataHoje}</td></tr>
</table></body></html>`;
    const blob = new Blob([html], {
      type: 'application/vnd.ms-excel;charset=utf-8',
    });
    const a = document.createElement('a');
    a.href = URL.createObjectURL(blob);
    a.download = `zettatecck-${tipo}-${
      new Date().toISOString().split('T')[0]
    }.xls`;
    a.click();
  }

  function exportPDF() {
    const rawData =
      tipo === 'pedidos'
        ? (() => {
            let d = pedidos;
            if (filtros.status !== 'all')
              d = d.filter((p) => p.status === filtros.status);
            if (filtros.pendencia !== 'all')
              d = d.filter((p) => p.pendencia === filtros.pendencia);
            if (filtros.anos && filtros.anos.length > 0) {
              d = d.filter((p) => {
                const af = p.data_fatura ? p.data_fatura.split('-')[0] : null;
                const ae = p.data_entrega ? p.data_entrega.split('-')[0] : null;
                return filtros.anos.includes(af) || filtros.anos.includes(ae);
              });
            }
            return d.map((p) => ({
              ...p,
              _itensHtml: itensHtml(p.itens_pendentes, p.pendencia),
            }));
          })()
        : null;

    const data = getData();
    const tipoLabel = {
      pedidos: 'Pedidos de Compra',
      projetos: 'Projetos',
      pagamentos: 'Pagamentos',
      fornecedores: 'Fornecedores',
    }[tipo];
    const dataHoje = new Date().toLocaleString('pt-BR');

    const buildCell = (col, row, idx) => {
      if (col === 'Itens Pendentes' && rawData) {
        return `<td>${rawData[idx]?._itensHtml || '—'}</td>`;
      }
      return `<td>${row[col] || '—'}</td>`;
    };

    const html = `<!DOCTYPE html><html><head><meta charset="utf-8"><title>Relatório Zettatecck</title>
    <style>
      *{box-sizing:border-box;margin:0;padding:0;}
      body{font-family:Arial,sans-serif;font-size:10px;color:#1E293B;background:#fff;}
      .header{background:linear-gradient(135deg,#0A0F1E,#0F3460);color:#fff;padding:20px 28px;display:flex;align-items:center;justify-content:space-between;}
      .logo-box{width:48px;height:48px;background:#00BCD4;border-radius:10px;display:flex;align-items:center;justify-content:center;font-size:22px;font-weight:900;color:#0A0F1E;}
      .company{color:#fff;font-size:16px;font-weight:900;}
      .company-sub{color:#22D3EE;font-size:9px;font-weight:600;text-transform:uppercase;letter-spacing:1px;margin-top:2px;}
      .report-title{color:#fff;font-size:13px;font-weight:700;text-align:right;}
      .report-date{color:#94A3B8;font-size:9px;margin-top:3px;text-align:right;}
      .meta-bar{background:#00BCD4;color:#0A0F1E;padding:8px 28px;font-size:9px;font-weight:700;display:flex;justify-content:space-between;}
      .content{padding:20px 28px;}
      table{width:100%;border-collapse:collapse;}
      thead tr{background:#0F172A;}
      th{color:#fff;padding:8px 10px;text-align:left;font-size:9px;font-weight:700;text-transform:uppercase;letter-spacing:0.5px;border:1px solid #1E293B;}
      td{padding:6px 10px;font-size:9px;border:1px solid #E2E8F0;vertical-align:top;}
      tr:nth-child(even) td{background:#F0FDFF;}
      tr:nth-child(odd) td{background:#fff;}
      .footer{background:#F8FAFC;border-top:2px solid #00BCD4;padding:10px 28px;display:flex;justify-content:space-between;font-size:8px;color:#64748B;margin-top:20px;}
      @media print{body{-webkit-print-color-adjust:exact;print-color-adjust:exact;}}
    </style></head><body>
    <div class="header">
      <div style="display:flex;align-items:center;gap:16px;">
        <img src="${LOGO}" style="width:52px;height:52px;border-radius:10px;object-fit:cover;" alt="Zettatecck"/>
        <div><div class="company">Zettatecck Projetos</div><div class="company-sub">Sistema de Gestão de Compras</div></div>
      </div>
      <div><div class="report-title">Relatório de ${tipoLabel}</div><div class="report-date">Gerado em ${dataHoje}</div></div>
    </div>
    <div class="meta-bar">
      <span>Total de registros: <strong>${data.length}</strong></span>
      <span>${selCols.join(' · ')}</span>
    </div>
    <div class="content">
      <table>
        <thead><tr>${selCols.map((c) => `<th>${c}</th>`).join('')}</tr></thead>
        <tbody>${data
          .map(
            (r, i) =>
              `<tr>${selCols.map((c) => buildCell(c, r, i)).join('')}</tr>`
          )
          .join('')}</tbody>
      </table>
    </div>
    <div class="footer">
      <span>⚡ <strong>Zettatecck Projetos</strong></span>
      <span>${data.length} registro(s) · ${dataHoje}</span>
    </div>
    </body></html>`;
    const w = window.open('', '_blank');
    if (!w) {
      alert('Permita pop-ups para exportar o PDF.');
      return;
    }
    w.document.write(html);
    w.document.close();
    w.onload = () => {
      setTimeout(() => w.print(), 300);
    };
  }
  const SB = (a) => ({
    padding: '9px 24px',
    border: 'none',
    borderRadius: 9,
    background: a ? '#00BCD4' : '#F1F5F9',
    color: a ? '#0A0F1E' : '#64748B',
    fontWeight: 800,
    fontSize: 13,
    cursor: 'pointer',
    fontFamily: 'inherit',
  });
  return (
    <div style={{ display: 'flex', flexDirection: 'column', gap: 16 }}>
      <div
        style={{
          background: '#fff',
          borderRadius: 14,
          padding: '18px 24px',
          boxShadow: '0 2px 8px rgba(0,0,0,.06)',
          display: 'flex',
          alignItems: 'center',
        }}
      >
        {[
          ['1', 'Escolher dados'],
          ['2', 'Selecionar colunas'],
          ['3', 'Exportar'],
        ].map(([n, l], i) => (
          <div
            key={n}
            style={{
              display: 'flex',
              alignItems: 'center',
              flex: i < 2 ? 1 : 'auto',
            }}
          >
            <div style={{ display: 'flex', alignItems: 'center', gap: 10 }}>
              <div
                style={{
                  width: 32,
                  height: 32,
                  borderRadius: '50%',
                  background: step >= parseInt(n) ? '#00BCD4' : '#F1F5F9',
                  color: step >= parseInt(n) ? '#0A0F1E' : '#94A3B8',
                  display: 'flex',
                  alignItems: 'center',
                  justifyContent: 'center',
                  fontWeight: 900,
                  fontSize: 14,
                }}
              >
                {n}
              </div>
              <span
                style={{
                  fontSize: 13,
                  fontWeight: step === parseInt(n) ? 700 : 500,
                  color: step === parseInt(n) ? '#0F172A' : '#94A3B8',
                }}
              >
                {l}
              </span>
            </div>
            {i < 2 && (
              <div
                style={{
                  flex: 1,
                  height: 2,
                  background: step > i + 1 ? '#00BCD4' : '#F1F5F9',
                  margin: '0 16px',
                }}
              />
            )}
          </div>
        ))}
      </div>
      {step === 1 && (
        <div
          style={{
            background: '#fff',
            borderRadius: 14,
            padding: 24,
            boxShadow: '0 2px 8px rgba(0,0,0,.06)',
          }}
        >
          <div style={{ fontWeight: 800, fontSize: 15, marginBottom: 20 }}>
            Passo 1 — Quais dados quer exportar?
          </div>
          <div
            style={{
              display: 'grid',
              gridTemplateColumns: 'repeat(auto-fit,minmax(160px,1fr))',
              gap: 12,
              marginBottom: 24,
            }}
          >
            {[
              ['pedidos', '📦', 'Pedidos de Compra'],
              ['projetos', '📁', 'Projetos'],
              ['pagamentos', '💳', 'Pagamentos'],
              ['fornecedores', '👥', 'Fornecedores'],
            ].map(([k, ic, l]) => (
              <button
                key={k}
                onClick={() => {
                  setTipo(k);
                  setFiltros({ status: 'all', pendencia: 'all', anos: [] });
                }}
                style={{
                  padding: '20px 16px',
                  border: `2px solid ${tipo === k ? '#00BCD4' : '#E2E8F0'}`,
                  borderRadius: 12,
                  background: tipo === k ? '#F0FDFF' : '#fff',
                  cursor: 'pointer',
                  fontFamily: 'inherit',
                  textAlign: 'center',
                }}
              >
                <div style={{ fontSize: 28, marginBottom: 6 }}>{ic}</div>
                <div
                  style={{
                    fontWeight: 700,
                    fontSize: 14,
                    color: tipo === k ? '#0E7490' : '#374151',
                  }}
                >
                  {l}
                </div>
              </button>
            ))}
          </div>
          {tipo === 'pedidos' && (
            <div
              style={{
                display: 'flex',
                flexDirection: 'column',
                gap: 12,
                padding: 16,
                background: '#F8FAFC',
                borderRadius: 10,
                marginBottom: 16,
              }}
            >
              <div style={{ display: 'flex', gap: 14, flexWrap: 'wrap' }}>
                <div>
                  <label style={LBL}>Filtrar por Status</label>
                  <select
                    style={{ ...INP, width: 'auto' }}
                    value={filtros.status}
                    onChange={(e) =>
                      setFiltros((f) => ({ ...f, status: e.target.value }))
                    }
                  >
                    <option value="all">Todos</option>
                    {[
                      'Concluído',
                      'Aguardando',
                      'Faturado Inicial',
                      'Entregue Parcial',
                    ].map((s) => (
                      <option key={s}>{s}</option>
                    ))}
                  </select>
                </div>
                <div>
                  <label style={LBL}>Filtrar por Pendência</label>
                  <select
                    style={{ ...INP, width: 'auto' }}
                    value={filtros.pendencia}
                    onChange={(e) =>
                      setFiltros((f) => ({ ...f, pendencia: e.target.value }))
                    }
                  >
                    <option value="all">Todas</option>
                    <option value="Sim">Com Pendência</option>
                    <option value="Não">Sem Pendência</option>
                  </select>
                </div>
              </div>
              {anosDisponiveis.length > 0 && (
                <div>
                  <label style={LBL}>
                    Filtrar por Ano (prazo fatura / entrega)
                  </label>
                  <div
                    style={{
                      display: 'flex',
                      gap: 8,
                      flexWrap: 'wrap',
                      marginTop: 4,
                    }}
                  >
                    <button
                      onClick={() => setFiltros((f) => ({ ...f, anos: [] }))}
                      style={{
                        padding: '6px 14px',
                        border: `2px solid ${
                          filtros.anos.length === 0 ? '#00BCD4' : '#E2E8F0'
                        }`,
                        borderRadius: 20,
                        background:
                          filtros.anos.length === 0 ? '#F0FDFF' : '#fff',
                        color:
                          filtros.anos.length === 0 ? '#0E7490' : '#64748B',
                        fontWeight: 700,
                        fontSize: 12,
                        cursor: 'pointer',
                        fontFamily: 'inherit',
                      }}
                    >
                      {filtros.anos.length === 0 ? '✓ ' : ''}Todos os anos
                    </button>
                    {anosDisponiveis.map((ano) => {
                      const sel = filtros.anos.includes(ano);
                      return (
                        <button
                          key={ano}
                          onClick={() =>
                            setFiltros((f) => ({
                              ...f,
                              anos: sel
                                ? f.anos.filter((a) => a !== ano)
                                : [...f.anos, ano],
                            }))
                          }
                          style={{
                            padding: '6px 14px',
                            border: `2px solid ${sel ? '#00BCD4' : '#E2E8F0'}`,
                            borderRadius: 20,
                            background: sel ? '#F0FDFF' : '#fff',
                            color: sel ? '#0E7490' : '#64748B',
                            fontWeight: 700,
                            fontSize: 12,
                            cursor: 'pointer',
                            fontFamily: 'inherit',
                          }}
                        >
                          {sel ? '✓ ' : ''}
                          {ano}
                        </button>
                      );
                    })}
                  </div>
                  {filtros.anos.length > 0 && (
                    <div
                      style={{
                        fontSize: 11,
                        color: '#0E7490',
                        marginTop: 6,
                        fontWeight: 600,
                      }}
                    >
                      📅 Filtrando anos: {filtros.anos.sort().join(', ')} —{' '}
                      {getData().length} pedido(s) encontrado(s)
                    </div>
                  )}
                </div>
              )}
            </div>
          )}
          <div style={{ display: 'flex', justifyContent: 'flex-end' }}>
            <button
              onClick={() => {
                selAll();
                setStep(2);
              }}
              style={SB(true)}
            >
              Próximo →
            </button>
          </div>
        </div>
      )}
      {step === 2 && (
        <div
          style={{
            background: '#fff',
            borderRadius: 14,
            padding: 24,
            boxShadow: '0 2px 8px rgba(0,0,0,.06)',
          }}
        >
          <div style={{ fontWeight: 800, fontSize: 15, marginBottom: 6 }}>
            Passo 2 — Quais colunas incluir?
          </div>
          <div style={{ fontSize: 13, color: '#64748B', marginBottom: 16 }}>
            Marque as informações que devem aparecer no relatório.
          </div>
          <div style={{ display: 'flex', gap: 8, marginBottom: 16 }}>
            <button
              onClick={selAll}
              style={{
                padding: '5px 14px',
                border: '1.5px solid #00BCD4',
                borderRadius: 8,
                background: 'none',
                color: '#0E7490',
                fontWeight: 700,
                fontSize: 12,
                cursor: 'pointer',
                fontFamily: 'inherit',
              }}
            >
              Selecionar tudo
            </button>
            <button
              onClick={() => setCols({})}
              style={{
                padding: '5px 14px',
                border: '1.5px solid #E2E8F0',
                borderRadius: 8,
                background: 'none',
                color: '#64748B',
                fontWeight: 700,
                fontSize: 12,
                cursor: 'pointer',
                fontFamily: 'inherit',
              }}
            >
              Limpar
            </button>
          </div>
          <div
            style={{
              display: 'flex',
              flexWrap: 'wrap',
              gap: 10,
              marginBottom: 20,
            }}
          >
            {COLS[tipo].map((c) => (
              <button
                key={c}
                onClick={() => toggleCol(c)}
                style={{
                  padding: '8px 16px',
                  border: `2px solid ${cols[c] ? '#00BCD4' : '#E2E8F0'}`,
                  borderRadius: 20,
                  background: cols[c] ? '#F0FDFF' : '#fff',
                  color: cols[c] ? '#0E7490' : '#64748B',
                  fontWeight: 600,
                  fontSize: 13,
                  cursor: 'pointer',
                  fontFamily: 'inherit',
                }}
              >
                {cols[c] ? '✓ ' : ''}
                {c}
              </button>
            ))}
          </div>
          {selCols.length > 0 && (
            <div
              style={{
                background: '#F8FAFC',
                borderRadius: 10,
                padding: 14,
                marginBottom: 16,
                overflowX: 'auto',
              }}
            >
              <div
                style={{
                  fontSize: 12,
                  color: '#64748B',
                  fontWeight: 700,
                  marginBottom: 8,
                }}
              >
                PRÉVIA — {getData().length} registros
              </div>
              <table style={{ borderCollapse: 'collapse', fontSize: 11 }}>
                <thead>
                  <tr>
                    {selCols.map((c) => (
                      <th
                        key={c}
                        style={{
                          padding: '5px 10px',
                          background: '#0F172A',
                          color: '#fff',
                          whiteSpace: 'nowrap',
                        }}
                      >
                        {c}
                      </th>
                    ))}
                  </tr>
                </thead>
                <tbody>
                  {getData()
                    .slice(0, 3)
                    .map((r, i) => (
                      <tr key={i}>
                        {selCols.map((c) => (
                          <td
                            key={c}
                            style={{
                              padding: '5px 10px',
                              borderBottom: '1px solid #E2E8F0',
                              whiteSpace: 'nowrap',
                            }}
                          >
                            {r[c] || '—'}
                          </td>
                        ))}
                      </tr>
                    ))}
                </tbody>
              </table>
              {getData().length > 3 && (
                <div style={{ fontSize: 11, color: '#94A3B8', marginTop: 6 }}>
                  ...e mais {getData().length - 3} registros
                </div>
              )}
            </div>
          )}
          <div style={{ display: 'flex', justifyContent: 'space-between' }}>
            <button onClick={() => setStep(1)} style={SB(false)}>
              ← Voltar
            </button>
            <button
              onClick={() => setStep(3)}
              disabled={selCols.length === 0}
              style={{
                ...SB(selCols.length > 0),
                opacity: selCols.length === 0 ? 0.4 : 1,
              }}
            >
              Próximo →
            </button>
          </div>
        </div>
      )}
      {step === 3 && (
        <div
          style={{
            background: '#fff',
            borderRadius: 14,
            padding: 24,
            boxShadow: '0 2px 8px rgba(0,0,0,.06)',
          }}
        >
          <div style={{ fontWeight: 800, fontSize: 15, marginBottom: 16 }}>
            Passo 3 — Exportar
          </div>
          <div
            style={{
              background: '#F8FAFC',
              borderRadius: 10,
              padding: 16,
              marginBottom: 24,
            }}
          >
            <div style={{ fontSize: 14, fontWeight: 700 }}>
              📊 {tipo.charAt(0).toUpperCase() + tipo.slice(1)} ·{' '}
              {getData().length} registros · {selCols.length} colunas
            </div>
            <div style={{ fontSize: 12, color: '#64748B', marginTop: 4 }}>
              Colunas: {selCols.join(', ')}
            </div>
          </div>
          <div
            style={{
              display: 'grid',
              gridTemplateColumns: '1fr 1fr',
              gap: 16,
              marginBottom: 24,
            }}
          >
            <button
              onClick={exportXLS}
              style={{
                padding: '20px',
                border: '2px solid #10B981',
                borderRadius: 12,
                background: '#F0FDF4',
                cursor: 'pointer',
                fontFamily: 'inherit',
                textAlign: 'center',
              }}
            >
              <div style={{ fontSize: 28, marginBottom: 6 }}>📥</div>
              <div style={{ fontWeight: 800, fontSize: 15, color: '#065F46' }}>
                Exportar Excel (.xls)
              </div>
              <div style={{ fontSize: 12, color: '#64748B', marginTop: 4 }}>
                Com layout e cores Zettatecck
              </div>
            </button>
            <button
              onClick={exportPDF}
              style={{
                padding: '20px',
                border: '2px solid #3B82F6',
                borderRadius: 12,
                background: '#EFF6FF',
                cursor: 'pointer',
                fontFamily: 'inherit',
                textAlign: 'center',
              }}
            >
              <div style={{ fontSize: 28, marginBottom: 6 }}>🖨️</div>
              <div style={{ fontWeight: 800, fontSize: 15, color: '#1E40AF' }}>
                Gerar PDF
              </div>
              <div style={{ fontSize: 12, color: '#64748B', marginTop: 4 }}>
                Abre para impressão/salvar
              </div>
            </button>
          </div>
          <div style={{ display: 'flex', justifyContent: 'space-between' }}>
            <button onClick={() => setStep(2)} style={SB(false)}>
              ← Voltar
            </button>
            <button
              onClick={() => {
                setStep(1);
                setCols({});
                setFiltros({ status: 'all', pendencia: 'all' });
              }}
              style={CANCEL_BTN}
            >
              Novo Relatório
            </button>
          </div>
        </div>
      )}
    </div>
  );
}

// ─── ANÁLISE POR PROJETO ──────────────────────────────────────────────────────
function AnaliseProjetoTab() {
  const { data: projetos, loading: lP } = useCRUD(
    'projetos',
    'order=numero.asc'
  );
  const { data: pedidos, loading: lPed } = useCRUD(
    'pedidos',
    'order=numero.asc'
  );
  const [search, setSearch] = useState('');
  const [fStatus, setFStatus] = useState('all');
  const [selecionado, setSelecionado] = useState(null);

  if (lP || lPed) return <Spin />;

  // monta lista de projetos com dados calculados
  const projetosComCalculo = projetos.map((proj) => {
    const pedidosDoProjeto = pedidos.filter(
      (p) => String(p.projeto) === String(proj.numero)
    );
    const totalPedidos = pedidosDoProjeto.reduce(
      (s, p) => s + (p.valor || 0),
      0
    );
    const pedidosConcluidos = pedidosDoProjeto.filter(
      (p) => p.status === 'Concluído'
    );
    const pedidosAbertos = pedidosDoProjeto.filter(
      (p) => p.status !== 'Concluído'
    );
    const totalConcluido = pedidosConcluidos.reduce(
      (s, p) => s + (p.valor || 0),
      0
    );
    const totalAberto = pedidosAbertos.reduce((s, p) => s + (p.valor || 0), 0);
    const saldo = (proj.max_compras || 0) - totalPedidos;
    const pctUsado =
      proj.max_compras > 0
        ? Math.round((totalPedidos / proj.max_compras) * 100)
        : 0;
    const isNestle = ['NESTLÉ', 'NESTLE', 'GAROTO', 'CPW', 'PURINA'].some((x) =>
      (proj.cliente || '').toUpperCase().includes(x)
    );
    const pctRegra = isNestle ? 30 : 40;
    return {
      ...proj,
      pedidos: pedidosDoProjeto,
      totalPedidos,
      totalConcluido,
      totalAberto,
      saldo,
      pctUsado,
      pctRegra,
      qtdPedidos: pedidosDoProjeto.length,
    };
  });

  const filtrados = projetosComCalculo.filter((p) => {
    const q = search.toLowerCase();
    if (
      q &&
      !String(p.numero).includes(q) &&
      !p.nome.toLowerCase().includes(q) &&
      !p.cliente.toLowerCase().includes(q)
    )
      return false;
    if (fStatus !== 'all' && p.status !== fStatus) return false;
    return true;
  });

  const projSel = selecionado
    ? projetosComCalculo.find((p) => p.id === selecionado)
    : null;

  function corSaldo(saldo) {
    if (saldo >= 0) return '#10B981';
    if (saldo > -5000) return '#F59E0B';
    return '#EF4444';
  }

  return (
    <div style={{ display: 'flex', gap: 16, alignItems: 'flex-start' }}>
      {/* LISTA DE PROJETOS */}
      <div
        style={{
          flex: 1,
          display: 'flex',
          flexDirection: 'column',
          gap: 12,
          minWidth: 0,
        }}
      >
        {/* filtros */}
        <div
          style={{
            background: '#fff',
            borderRadius: 12,
            padding: '12px 16px',
            display: 'flex',
            gap: 10,
            flexWrap: 'wrap',
            boxShadow: '0 1px 4px rgba(0,0,0,.06)',
          }}
        >
          <input
            value={search}
            onChange={(e) => setSearch(e.target.value)}
            placeholder="🔍 Buscar por número, nome, cliente..."
            style={{ ...INP, flex: 1, minWidth: 180 }}
          />
          <select
            value={fStatus}
            onChange={(e) => setFStatus(e.target.value)}
            style={{ ...INP, width: 'auto' }}
          >
            <option value="all">Todos</option>
            <option value="ENTREGUE">Entregue</option>
            <option value="ENTREGUE PARCIAL">Entregue Parcial</option>
            <option value="NÃO ENTREGUE">Não Entregue</option>
            <option value="SEM ENTREGA">Sem Entrega</option>
          </select>
          <span style={{ alignSelf: 'center', fontSize: 12, color: '#94A3B8' }}>
            {filtrados.length} projetos
          </span>
        </div>

        {/* cards de projetos */}
        {filtrados.map((p) => (
          <div
            key={p.id}
            onClick={() => setSelecionado(selecionado === p.id ? null : p.id)}
            style={{
              background: '#fff',
              borderRadius: 14,
              padding: '16px 20px',
              boxShadow:
                selecionado === p.id
                  ? '0 0 0 2px #00BCD4, 0 4px 16px rgba(0,188,212,.15)'
                  : '0 2px 8px rgba(0,0,0,.06)',
              cursor: 'pointer',
              transition: 'all .15s',
              borderLeft: `4px solid ${
                p.saldo >= 0
                  ? '#10B981'
                  : p.saldo > -5000
                  ? '#F59E0B'
                  : '#EF4444'
              }`,
            }}
          >
            {/* LINHA 1: número + badges + nome */}
            <div
              style={{
                display: 'flex',
                alignItems: 'center',
                gap: 10,
                marginBottom: 4,
                flexWrap: 'wrap',
              }}
            >
              <span
                style={{
                  fontWeight: 900,
                  fontSize: 15,
                  color: '#3B82F6',
                  flexShrink: 0,
                }}
              >
                #{p.numero}
              </span>
              <Badge s={p.status} />
              <span
                style={{
                  fontSize: 11,
                  fontWeight: 600,
                  background: p.pctRegra === 30 ? '#DCFCE7' : '#DBEAFE',
                  color: p.pctRegra === 30 ? '#166534' : '#1E40AF',
                  padding: '2px 8px',
                  borderRadius: 10,
                  flexShrink: 0,
                }}
              >
                {p.pctRegra === 30 ? 'Nestlé 30%' : 'Cliente 40%'}
              </span>
            </div>

            {/* LINHA 2: nome do projeto */}
            <div
              style={{
                fontWeight: 700,
                fontSize: 14,
                color: '#0F172A',
                marginBottom: 2,
                overflow: 'hidden',
                textOverflow: 'ellipsis',
                whiteSpace: 'nowrap',
              }}
            >
              {p.nome}
            </div>
            <div style={{ fontSize: 12, color: '#64748B', marginBottom: 12 }}>
              {p.cliente} · {p.cidade}
            </div>

            {/* LINHA 3: 4 valores lado a lado */}
            <div
              style={{
                display: 'grid',
                gridTemplateColumns: 'repeat(4,1fr)',
                gap: 8,
                marginBottom: 12,
              }}
            >
              {[
                ['Valor Projeto', fmt(p.valor), '#0F172A'],
                ['Máx. Compras', fmt(p.max_compras), '#8B5CF6'],
                ['Total Pedidos', fmt(p.totalPedidos), '#374151'],
                [
                  'Saldo',
                  `${p.saldo >= 0 ? '+' : ''}${fmt(p.saldo)}`,
                  corSaldo(p.saldo),
                ],
              ].map(([l, v, c]) => (
                <div
                  key={l}
                  style={{
                    background: '#F8FAFC',
                    borderRadius: 8,
                    padding: '8px 10px',
                  }}
                >
                  <div
                    style={{
                      fontSize: 10,
                      color: '#94A3B8',
                      fontWeight: 700,
                      textTransform: 'uppercase',
                      letterSpacing: 0.3,
                      marginBottom: 3,
                    }}
                  >
                    {l}
                  </div>
                  <div style={{ fontWeight: 800, fontSize: 13, color: c }}>
                    {v}
                  </div>
                </div>
              ))}
            </div>

            {/* LINHA 4: barra de progresso */}
            <div
              style={{
                display: 'flex',
                justifyContent: 'space-between',
                marginBottom: 4,
              }}
            >
              <span style={{ fontSize: 11, color: '#64748B' }}>
                {p.qtdPedidos} pedido{p.qtdPedidos !== 1 ? 's' : ''} vinculado
                {p.qtdPedidos !== 1 ? 's' : ''}
              </span>
              <span
                style={{
                  fontSize: 11,
                  fontWeight: 700,
                  color:
                    p.pctUsado > 100
                      ? '#EF4444'
                      : p.pctUsado > 80
                      ? '#F59E0B'
                      : '#10B981',
                }}
              >
                {p.pctUsado}% do limite
              </span>
            </div>
            <div
              style={{
                background: '#F1F5F9',
                borderRadius: 6,
                height: 7,
                overflow: 'hidden',
              }}
            >
              <div
                style={{
                  background:
                    p.pctUsado > 100
                      ? '#EF4444'
                      : p.pctUsado > 80
                      ? '#F59E0B'
                      : '#10B981',
                  borderRadius: 6,
                  height: 7,
                  width: `${Math.min(p.pctUsado, 100)}%`,
                  transition: 'width .5s',
                }}
              />
            </div>
            {p.pctUsado > 100 && (
              <div
                style={{
                  fontSize: 11,
                  color: '#EF4444',
                  fontWeight: 700,
                  marginTop: 4,
                }}
              >
                ⚠️ Limite excedido em {fmt(Math.abs(p.saldo))}
              </div>
            )}
            {selecionado === p.id && (
              <div
                style={{
                  marginTop: 8,
                  fontSize: 11,
                  color: '#00BCD4',
                  fontWeight: 600,
                  textAlign: 'center',
                }}
              >
                ▲ Clique para fechar detalhes
              </div>
            )}
          </div>
        ))}
        {filtrados.length === 0 && (
          <div
            style={{
              background: '#fff',
              borderRadius: 14,
              padding: 48,
              textAlign: 'center',
              color: '#94A3B8',
              boxShadow: '0 2px 8px rgba(0,0,0,.06)',
            }}
          >
            Nenhum projeto encontrado
          </div>
        )}
      </div>

      {/* PAINEL DE DETALHES */}
      {projSel && (
        <div
          style={{
            width: 520,
            flexShrink: 0,
            display: 'flex',
            flexDirection: 'column',
            gap: 14,
            position: 'sticky',
            top: 24,
          }}
        >
          {/* HEADER DO PAINEL */}
          <div
            style={{
              background: 'linear-gradient(135deg,#0A0F1E 0%,#0F3460 100%)',
              borderRadius: 16,
              overflow: 'hidden',
              boxShadow: '0 8px 24px rgba(0,0,0,.2)',
            }}
          >
            {/* topo ciano */}
            <div
              style={{
                background: '#00BCD4',
                padding: '10px 20px',
                display: 'flex',
                justifyContent: 'space-between',
                alignItems: 'center',
              }}
            >
              <span
                style={{
                  fontSize: 11,
                  fontWeight: 800,
                  color: '#0A0F1E',
                  textTransform: 'uppercase',
                  letterSpacing: 1,
                }}
              >
                📋 Análise do Projeto
              </span>
              <button
                onClick={() => setSelecionado(null)}
                style={{
                  background: 'rgba(0,0,0,.15)',
                  border: 'none',
                  borderRadius: 6,
                  width: 26,
                  height: 26,
                  color: '#0A0F1E',
                  cursor: 'pointer',
                  fontSize: 14,
                  fontWeight: 700,
                  display: 'flex',
                  alignItems: 'center',
                  justifyContent: 'center',
                }}
              >
                ✕
              </button>
            </div>
            {/* conteúdo do header */}
            <div style={{ padding: '18px 20px' }}>
              <div
                style={{
                  fontSize: 12,
                  color: '#22D3EE',
                  fontWeight: 700,
                  letterSpacing: 0.5,
                  marginBottom: 6,
                }}
              >
                Projeto #{projSel.numero}
              </div>
              <div
                style={{
                  fontSize: 17,
                  fontWeight: 900,
                  color: '#fff',
                  lineHeight: 1.3,
                  marginBottom: 4,
                }}
              >
                {projSel.nome || '—'}
              </div>
              <div style={{ fontSize: 13, color: '#94A3B8' }}>
                {projSel.cliente || '—'}
                {projSel.cidade ? ` · ${projSel.cidade}` : ''}
              </div>
              <div style={{ marginTop: 12, display: 'flex', gap: 8 }}>
                <Badge s={projSel.status} />
                <span
                  style={{
                    fontSize: 11,
                    fontWeight: 700,
                    background:
                      projSel.pctRegra === 30
                        ? 'rgba(16,185,129,.2)'
                        : 'rgba(59,130,246,.2)',
                    color: projSel.pctRegra === 30 ? '#34D399' : '#60A5FA',
                    padding: '3px 10px',
                    borderRadius: 20,
                  }}
                >
                  {projSel.pctRegra === 30 ? 'Nestlé — 30%' : 'Cliente — 40%'}
                </span>
              </div>
            </div>
            {/* 4 KPIs */}
            <div
              style={{
                display: 'grid',
                gridTemplateColumns: '1fr 1fr',
                gap: 1,
                background: 'rgba(255,255,255,.06)',
              }}
            >
              {[
                ['Valor do Projeto', fmt(projSel.valor), '#fff'],
                ['Máx. Compras', fmt(projSel.max_compras), '#A78BFA'],
                ['Total em Pedidos', fmt(projSel.totalPedidos), '#FCD34D'],
                [
                  projSel.saldo >= 0 ? 'Saldo Disponível' : 'Limite Excedido',
                  `${projSel.saldo >= 0 ? '+' : ''}${fmt(projSel.saldo)}`,
                  projSel.saldo >= 0 ? '#34D399' : '#F87171',
                ],
              ].map(([l, v, c]) => (
                <div
                  key={l}
                  style={{ padding: '14px 18px', background: 'rgba(0,0,0,.2)' }}
                >
                  <div
                    style={{
                      fontSize: 10,
                      color: '#64748B',
                      fontWeight: 700,
                      textTransform: 'uppercase',
                      letterSpacing: 0.5,
                      marginBottom: 4,
                    }}
                  >
                    {l}
                  </div>
                  <div style={{ fontSize: 16, fontWeight: 900, color: c }}>
                    {v}
                  </div>
                </div>
              ))}
            </div>
            {/* barra de uso */}
            <div style={{ padding: '14px 20px' }}>
              <div
                style={{
                  display: 'flex',
                  justifyContent: 'space-between',
                  marginBottom: 6,
                }}
              >
                <span style={{ fontSize: 11, color: '#94A3B8' }}>
                  Utilização do limite ({projSel.pctRegra}%)
                </span>
                <span
                  style={{
                    fontSize: 12,
                    fontWeight: 800,
                    color:
                      projSel.pctUsado > 100
                        ? '#F87171'
                        : projSel.pctUsado > 80
                        ? '#FCD34D'
                        : '#34D399',
                  }}
                >
                  {projSel.pctUsado}%
                </span>
              </div>
              <div
                style={{
                  background: 'rgba(255,255,255,.1)',
                  borderRadius: 6,
                  height: 10,
                  overflow: 'hidden',
                }}
              >
                <div
                  style={{
                    background:
                      projSel.pctUsado > 100
                        ? '#EF4444'
                        : projSel.pctUsado > 80
                        ? '#F59E0B'
                        : '#10B981',
                    borderRadius: 6,
                    height: 10,
                    width: `${Math.min(projSel.pctUsado, 100)}%`,
                    transition: 'width .6s',
                  }}
                />
              </div>
              {projSel.saldo < 0 && (
                <div
                  style={{
                    marginTop: 8,
                    fontSize: 11,
                    color: '#F87171',
                    fontWeight: 700,
                  }}
                >
                  ⚠️ Limite excedido em {fmt(Math.abs(projSel.saldo))}
                </div>
              )}
            </div>
          </div>

          {/* RESUMO FINANCEIRO */}
          <div
            style={{
              background: '#fff',
              borderRadius: 14,
              padding: '18px 20px',
              boxShadow: '0 2px 8px rgba(0,0,0,.06)',
            }}
          >
            <div
              style={{
                fontWeight: 800,
                fontSize: 14,
                color: '#0F172A',
                marginBottom: 14,
                display: 'flex',
                alignItems: 'center',
                gap: 8,
              }}
            >
              💰 Resumo Financeiro
            </div>
            <div style={{ display: 'flex', flexDirection: 'column', gap: 0 }}>
              {[
                ['Pedidos concluídos', fmt(projSel.totalConcluido), '#10B981'],
                ['Pedidos em aberto', fmt(projSel.totalAberto), '#F59E0B'],
                [
                  'Total geral em pedidos',
                  fmt(projSel.totalPedidos),
                  '#3B82F6',
                ],
                [
                  'Limite máximo de compras',
                  fmt(projSel.max_compras),
                  '#8B5CF6',
                ],
                [
                  projSel.saldo >= 0 ? 'Saldo restante' : 'Limite excedido',
                  `${projSel.saldo >= 0 ? '+' : ''}${fmt(projSel.saldo)}`,
                  projSel.saldo >= 0 ? '#10B981' : '#EF4444',
                ],
              ].map(([l, v, c], i, arr) => (
                <div
                  key={l}
                  style={{
                    display: 'flex',
                    justifyContent: 'space-between',
                    alignItems: 'center',
                    padding: '10px 0',
                    borderBottom:
                      i < arr.length - 1 ? '1px solid #F1F5F9' : 'none',
                  }}
                >
                  <span style={{ fontSize: 13, color: '#374151' }}>{l}</span>
                  <span style={{ fontSize: 14, fontWeight: 800, color: c }}>
                    {v}
                  </span>
                </div>
              ))}
            </div>
            {projSel.saldo < 0 && (
              <div
                style={{
                  marginTop: 12,
                  background: '#FEF2F2',
                  border: '1px solid #FECACA',
                  borderRadius: 10,
                  padding: '10px 14px',
                  fontSize: 12,
                  color: '#991B1B',
                  fontWeight: 600,
                }}
              >
                ⚠️ Ultrapassou o limite em{' '}
                <strong>{fmt(Math.abs(projSel.saldo))}</strong>
              </div>
            )}
          </div>

          {/* GRÁFICO POR FORNECEDOR */}
          {projSel.pedidos.length > 0 &&
            (() => {
              const CORES = [
                '#00BCD4',
                '#8B5CF6',
                '#F59E0B',
                '#10B981',
                '#EF4444',
                '#3B82F6',
                '#F97316',
                '#EC4899',
              ];
              const porForn = Object.entries(
                projSel.pedidos.reduce((acc, p) => {
                  acc[p.fornecedor || 'Outros'] =
                    (acc[p.fornecedor || 'Outros'] || 0) + (p.valor || 0);
                  return acc;
                }, {})
              ).sort((a, b) => b[1] - a[1]);
              const total = projSel.totalPedidos || 1;
              return (
                <div
                  style={{
                    background: '#fff',
                    borderRadius: 14,
                    padding: '18px 20px',
                    boxShadow: '0 2px 8px rgba(0,0,0,.06)',
                  }}
                >
                  <div
                    style={{
                      fontWeight: 800,
                      fontSize: 14,
                      color: '#0F172A',
                      marginBottom: 14,
                    }}
                  >
                    📊 Gasto por Fornecedor
                  </div>
                  {/* barra empilhada */}
                  <div
                    style={{
                      display: 'flex',
                      borderRadius: 8,
                      overflow: 'hidden',
                      height: 20,
                      marginBottom: 14,
                    }}
                  >
                    {porForn.map(([nome, val], i) => (
                      <div
                        key={nome}
                        title={`${nome}: ${fmt(val)} (${Math.round(
                          (val / total) * 100
                        )}%)`}
                        style={{
                          width: `${(val / total) * 100}%`,
                          background: CORES[i % CORES.length],
                          transition: 'width .4s',
                        }}
                      />
                    ))}
                  </div>
                  {/* legenda */}
                  <div
                    style={{ display: 'flex', flexDirection: 'column', gap: 8 }}
                  >
                    {porForn.map(([nome, val], i) => {
                      const pct = Math.round((val / total) * 100);
                      return (
                        <div
                          key={nome}
                          style={{
                            display: 'flex',
                            alignItems: 'center',
                            gap: 10,
                          }}
                        >
                          <div
                            style={{
                              width: 12,
                              height: 12,
                              borderRadius: 3,
                              background: CORES[i % CORES.length],
                              flexShrink: 0,
                            }}
                          />
                          <div
                            style={{
                              flex: 1,
                              fontSize: 12,
                              color: '#374151',
                              fontWeight: 500,
                              overflow: 'hidden',
                              textOverflow: 'ellipsis',
                              whiteSpace: 'nowrap',
                            }}
                          >
                            {nome}
                          </div>
                          <div
                            style={{
                              fontSize: 12,
                              fontWeight: 700,
                              color: '#0F172A',
                            }}
                          >
                            {fmt(val)}
                          </div>
                          <div
                            style={{
                              fontSize: 11,
                              fontWeight: 700,
                              color: CORES[i % CORES.length],
                              minWidth: 36,
                              textAlign: 'right',
                            }}
                          >
                            {pct}%
                          </div>
                        </div>
                      );
                    })}
                  </div>
                </div>
              );
            })()}

          {/* PEDIDOS VINCULADOS */}
          <div
            style={{
              background: '#fff',
              borderRadius: 14,
              boxShadow: '0 2px 8px rgba(0,0,0,.06)',
              overflow: 'hidden',
            }}
          >
            <div
              style={{
                padding: '14px 20px',
                borderBottom: '1px solid #F1F5F9',
                display: 'flex',
                justifyContent: 'space-between',
                alignItems: 'center',
              }}
            >
              <span style={{ fontWeight: 800, fontSize: 14, color: '#0F172A' }}>
                📦 Pedidos Vinculados
              </span>
              <span
                style={{
                  fontSize: 12,
                  color: '#64748B',
                  background: '#F1F5F9',
                  padding: '3px 10px',
                  borderRadius: 20,
                  fontWeight: 600,
                }}
              >
                {projSel.qtdPedidos} pedido{projSel.qtdPedidos !== 1 ? 's' : ''}
              </span>
            </div>
            {projSel.pedidos.length === 0 ? (
              <div
                style={{
                  padding: 32,
                  textAlign: 'center',
                  color: '#94A3B8',
                  fontSize: 13,
                }}
              >
                Nenhum pedido vinculado a este projeto
              </div>
            ) : (
              <div style={{ maxHeight: 300, overflowY: 'auto' }}>
                {projSel.pedidos.map((ped, i) => (
                  <div
                    key={ped.id}
                    style={{
                      padding: '12px 20px',
                      borderBottom: '1px solid #F8FAFC',
                      display: 'flex',
                      justifyContent: 'space-between',
                      alignItems: 'flex-start',
                      gap: 12,
                      background: i % 2 ? '#FAFBFC' : '#fff',
                    }}
                  >
                    <div style={{ flex: 1, minWidth: 0 }}>
                      <div
                        style={{
                          display: 'flex',
                          alignItems: 'center',
                          gap: 6,
                          marginBottom: 4,
                          flexWrap: 'wrap',
                        }}
                      >
                        <span
                          style={{
                            fontWeight: 800,
                            fontSize: 13,
                            color: '#8B5CF6',
                          }}
                        >
                          #{ped.numero}
                        </span>
                        <Badge s={ped.status} />
                        {ped.pendencia === 'Sim' && (
                          <span
                            style={{
                              fontSize: 10,
                              fontWeight: 700,
                              color: '#EF4444',
                              background: '#FEE2E2',
                              padding: '1px 7px',
                              borderRadius: 8,
                            }}
                          >
                            PENDÊNCIA
                          </span>
                        )}
                      </div>
                      <div
                        style={{
                          fontSize: 12,
                          color: '#374151',
                          fontWeight: 600,
                          marginBottom: 2,
                        }}
                      >
                        {ped.fornecedor || '—'}
                      </div>
                      {ped.nfe && (
                        <div style={{ fontSize: 11, color: '#64748B' }}>
                          NF-e: {ped.nfe}
                        </div>
                      )}
                      {ped.data_entrega && (
                        <div style={{ fontSize: 11, color: '#94A3B8' }}>
                          Entrega: {fmtDate(ped.data_entrega)}
                        </div>
                      )}
                    </div>
                    <div style={{ textAlign: 'right', flexShrink: 0 }}>
                      <div
                        style={{
                          fontWeight: 800,
                          fontSize: 14,
                          color: '#0F172A',
                        }}
                      >
                        {fmt(ped.valor)}
                      </div>
                    </div>
                  </div>
                ))}
              </div>
            )}
            {projSel.pedidos.length > 0 && (
              <div
                style={{
                  padding: '10px 20px',
                  borderTop: '2px solid #F1F5F9',
                  display: 'flex',
                  justifyContent: 'space-between',
                  alignItems: 'center',
                  background: '#F8FAFC',
                }}
              >
                <span style={{ fontSize: 12, color: '#64748B' }}>
                  Total investido
                </span>
                <span
                  style={{ fontSize: 14, fontWeight: 900, color: '#0F172A' }}
                >
                  {fmt(projSel.totalPedidos)}
                </span>
              </div>
            )}
          </div>
        </div>
      )}
    </div>
  );
}

// ─── EDITAR PERFIL ────────────────────────────────────────────────────────────
function EditarPerfil({ usuario, onClose, onUpdate }) {
  const [nome, setNome] = useState(usuario.nome || '');
  const [email, setEmail] = useState(usuario.email || '');
  const [senhaAtual, setSenhaAtual] = useState('');
  const [novaSenha, setNovaSenha] = useState('');
  const [confSenha, setConfSenha] = useState('');
  const [erro, setErro] = useState('');
  const [ok, setOk] = useState('');
  const [saving, setSaving] = useState(false);

  async function salvar(e) {
    e.preventDefault();
    setErro('');
    setOk('');
    if (!nome.trim()) {
      setErro('O nome não pode estar vazio.');
      return;
    }
    if (!validarNome(nome)) {
      setErro('Digite nome e sobrenome. Ex: Maria Silva');
      return;
    }
    const nomeFormatado = formatarNome(nome);
    if (novaSenha || senhaAtual || confSenha) {
      if (senhaAtual !== usuario.senha) {
        setErro('Senha atual incorreta.');
        return;
      }
      if (novaSenha.length < 6) {
        setErro('A nova senha deve ter pelo menos 6 caracteres.');
        return;
      }
      if (novaSenha !== confSenha) {
        setErro('As senhas não coincidem.');
        return;
      }
    }
    setSaving(true);
    try {
      const updates = { nome: nomeFormatado, email: email.trim() };
      if (novaSenha) updates.senha = novaSenha;
      await sbUpdate('usuarios', usuario.id, updates);
      onUpdate({ ...usuario, ...updates });
      setOk('Perfil atualizado com sucesso!');
      setSenhaAtual('');
      setNovaSenha('');
      setConfSenha('');
    } catch (err) {
      setErro('Erro ao salvar. Tente novamente.');
    } finally {
      setSaving(false);
    }
  }

  return (
    <Modal title="✏️ Editar Meu Perfil" onClose={onClose}>
      <form
        onSubmit={salvar}
        style={{ display: 'flex', flexDirection: 'column', gap: 14 }}
      >
        <div
          style={{
            display: 'flex',
            alignItems: 'center',
            gap: 14,
            padding: '12px 16px',
            background: '#F8FAFC',
            borderRadius: 10,
            marginBottom: 4,
          }}
        >
          <div
            style={{
              width: 48,
              height: 48,
              borderRadius: '50%',
              background: '#00BCD4',
              display: 'flex',
              alignItems: 'center',
              justifyContent: 'center',
              fontWeight: 900,
              fontSize: 20,
              color: '#0A0F1E',
              flexShrink: 0,
            }}
          >
            {nome[0]?.toUpperCase() || '?'}
          </div>
          <div>
            <div style={{ fontWeight: 700, fontSize: 15 }}>{usuario.nome}</div>
            <div style={{ fontSize: 12, color: '#64748B' }}>
              {usuario.perfil}
            </div>
          </div>
        </div>
        {erro && (
          <div
            style={{
              background: '#FEE2E2',
              color: '#991B1B',
              padding: '10px 14px',
              borderRadius: 8,
              fontSize: 13,
              fontWeight: 600,
            }}
          >
            ⚠️ {erro}
          </div>
        )}
        {ok && (
          <div
            style={{
              background: '#D1FAE5',
              color: '#065F46',
              padding: '10px 14px',
              borderRadius: 8,
              fontSize: 13,
              fontWeight: 600,
            }}
          >
            ✅ {ok}
          </div>
        )}
        <div>
          <label style={LBL}>Nome</label>
          <input
            style={INP}
            value={nome}
            onChange={(e) => setNome(e.target.value)}
            placeholder="Nome e Sobrenome"
          />
          {nome && validarNome(nome) && (
            <div style={{ fontSize: 11, color: '#10B981', marginTop: 4 }}>
              ✓ Será salvo como: <strong>{formatarNome(nome)}</strong>
            </div>
          )}
          {nome && !validarNome(nome) && (
            <div style={{ fontSize: 11, color: '#EF4444', marginTop: 4 }}>
              ⚠️ Digite nome e sobrenome
            </div>
          )}
        </div>
        <div>
          <label style={LBL}>E-mail</label>
          <input
            style={INP}
            type="email"
            value={email}
            onChange={(e) => setEmail(e.target.value)}
          />
        </div>
        <div
          style={{
            borderTop: '1px solid #F1F5F9',
            paddingTop: 14,
            marginTop: 4,
          }}
        >
          <div
            style={{
              fontSize: 12,
              fontWeight: 700,
              color: '#64748B',
              marginBottom: 12,
              textTransform: 'uppercase',
              letterSpacing: 0.5,
            }}
          >
            🔒 Alterar Senha (opcional)
          </div>
          <div style={{ display: 'flex', flexDirection: 'column', gap: 12 }}>
            <div>
              <label style={LBL}>Senha atual</label>
              <input
                style={INP}
                type="password"
                value={senhaAtual}
                onChange={(e) => setSenhaAtual(e.target.value)}
                placeholder="Digite sua senha atual"
              />
            </div>
            <div>
              <label style={LBL}>Nova senha</label>
              <input
                style={INP}
                type="password"
                value={novaSenha}
                onChange={(e) => setNovaSenha(e.target.value)}
                placeholder="Mínimo 6 caracteres"
              />
            </div>
            <div>
              <label style={LBL}>Confirmar nova senha</label>
              <input
                style={INP}
                type="password"
                value={confSenha}
                onChange={(e) => setConfSenha(e.target.value)}
                placeholder="Repita a nova senha"
              />
            </div>
          </div>
        </div>
        <div
          style={{
            display: 'flex',
            gap: 10,
            justifyContent: 'flex-end',
            marginTop: 6,
          }}
        >
          <button type="button" onClick={onClose} style={CANCEL_BTN}>
            Cancelar
          </button>
          <button
            type="submit"
            disabled={saving}
            style={{ ...SAVE_BTN, opacity: saving ? 0.7 : 1 }}
          >
            {saving ? 'Salvando...' : '💾 Salvar Alterações'}
          </button>
        </div>
      </form>
    </Modal>
  );
}

// ─── APP ROOT ─────────────────────────────────────────────────────────────────
export default function App() {
  const [usuario, setUsuario] = useState(null);
  const [tab, setTab] = useState('dashboard');
  const [pendCount, setPendCount] = useState(0);
  const [editandoPerfil, setEditandoPerfil] = useState(false);
  const isAdmin = usuario?.perfil === 'Administrador';

  useEffect(() => {
    if (!isAdmin) return;
    sbGet('usuarios', 'status=eq.pendente&select=id')
      .then((d) => setPendCount(d.length))
      .catch(() => {});
    const interval = setInterval(() => {
      sbGet('usuarios', 'status=eq.pendente&select=id')
        .then((d) => setPendCount(d.length))
        .catch(() => {});
    }, 30000);
    return () => clearInterval(interval);
  }, [isAdmin]);

  const TABS = [
    { id: 'dashboard', label: '📊 Dashboard' },
    { id: 'projetos', label: '📁 Projetos' },
    { id: 'pedidos', label: '📦 Pedidos' },
    { id: 'pagamentos', label: '💳 Pagamentos' },
    { id: 'fornecedores', label: '👥 Fornecedores' },
    { id: 'analise', label: '📋 Análise por Projeto' },
    { id: 'relatorio', label: '📤 Relatório' },
    ...(isAdmin
      ? [
          {
            id: 'usuarios',
            label: `👤 Usuários${pendCount > 0 ? ` (${pendCount})` : ''}`,
          },
        ]
      : []),
  ];

  if (!usuario) return <Login onLogin={setUsuario} />;

  return (
    <div
      style={{
        minHeight: '100vh',
        background: '#F0F4F8',
        fontFamily: "'IBM Plex Sans','Segoe UI',sans-serif",
      }}
    >
      {editandoPerfil && (
        <EditarPerfil
          usuario={usuario}
          onClose={() => setEditandoPerfil(false)}
          onUpdate={(u) => {
            setUsuario(u);
            setEditandoPerfil(false);
          }}
        />
      )}
      <div
        style={{
          background: 'linear-gradient(135deg,#0A0F1E 0%,#0F3460 100%)',
          color: '#fff',
        }}
      >
        <div style={{ width: '100%', padding: '0 24px' }}>
          <div
            style={{
              display: 'flex',
              alignItems: 'center',
              justifyContent: 'space-between',
              padding: '14px 0 0',
            }}
          >
            <div style={{ display: 'flex', alignItems: 'center', gap: 16 }}>
              <img
                src={LOGO}
                alt="Zettatecck"
                style={{
                  width: 48,
                  height: 48,
                  borderRadius: 10,
                  objectFit: 'cover',
                  boxShadow: '0 4px 16px rgba(0,188,212,.3)',
                }}
              />
              <div
                style={{
                  width: 1,
                  height: 36,
                  background: 'rgba(255,255,255,.15)',
                }}
              />
              <div>
                <div
                  style={{ fontSize: 16, fontWeight: 900, letterSpacing: -0.3 }}
                >
                  Zettatecck Projetos
                </div>
                <div
                  style={{
                    fontSize: 10,
                    color: '#22D3EE',
                    fontWeight: 600,
                    letterSpacing: 0.6,
                    textTransform: 'uppercase',
                  }}
                >
                  Sistema de Gestão de Compras
                </div>
              </div>
            </div>
            <div style={{ display: 'flex', alignItems: 'center', gap: 10 }}>
              {pendCount > 0 && isAdmin && (
                <div
                  style={{
                    background: '#EF4444',
                    color: '#fff',
                    borderRadius: 20,
                    padding: '4px 12px',
                    fontSize: 12,
                    fontWeight: 700,
                  }}
                >
                  ⏳ {pendCount} pendente{pendCount > 1 ? 's' : ''}
                </div>
              )}
              <button
                onClick={() => setEditandoPerfil(true)}
                title="Editar meu perfil"
                style={{
                  display: 'flex',
                  alignItems: 'center',
                  gap: 10,
                  background: 'rgba(255,255,255,.06)',
                  border: '1px solid rgba(255,255,255,.12)',
                  borderRadius: 10,
                  padding: '6px 12px',
                  cursor: 'pointer',
                }}
                onMouseEnter={(e) =>
                  (e.currentTarget.style.background = 'rgba(255,255,255,.12)')
                }
                onMouseLeave={(e) =>
                  (e.currentTarget.style.background = 'rgba(255,255,255,.06)')
                }
              >
                <div
                  style={{
                    width: 30,
                    height: 30,
                    borderRadius: '50%',
                    background: '#22D3EE',
                    display: 'flex',
                    alignItems: 'center',
                    justifyContent: 'center',
                    fontWeight: 900,
                    fontSize: 13,
                    color: '#0A0F1E',
                  }}
                >
                  {usuario.nome[0].toUpperCase()}
                </div>
                <div style={{ textAlign: 'left' }}>
                  <div style={{ fontSize: 13, fontWeight: 700, color: '#fff' }}>
                    {usuario.nome}
                  </div>
                  <div style={{ fontSize: 10, color: '#22D3EE' }}>
                    {usuario.perfil} · ✏️ editar perfil
                  </div>
                </div>
              </button>
              <button
                onClick={() => setUsuario(null)}
                style={{
                  padding: '7px 14px',
                  background: 'rgba(255,255,255,.08)',
                  border: '1px solid rgba(255,255,255,.15)',
                  borderRadius: 8,
                  color: '#94A3B8',
                  fontSize: 12,
                  fontWeight: 600,
                  cursor: 'pointer',
                  fontFamily: 'inherit',
                }}
              >
                Sair
              </button>
            </div>
          </div>
          <div
            style={{
              display: 'flex',
              gap: 1,
              marginTop: 12,
              overflowX: 'auto',
            }}
          >
            {TABS.map((t) => (
              <button
                key={t.id}
                onClick={() => setTab(t.id)}
                style={{
                  padding: '9px 16px',
                  background: tab === t.id ? '#fff' : 'transparent',
                  border: 'none',
                  borderRadius: '8px 8px 0 0',
                  color: tab === t.id ? '#0F172A' : '#94A3B8',
                  fontWeight: tab === t.id ? 800 : 500,
                  fontSize: 12,
                  cursor: 'pointer',
                  fontFamily: 'inherit',
                  whiteSpace: 'nowrap',
                }}
              >
                {t.label}
              </button>
            ))}
          </div>
        </div>
      </div>
      <div style={{ width: '100%', padding: '20px 24px' }}>
        {tab === 'dashboard' && <Dashboard />}
        {tab === 'projetos' && <ProjetosTab />}
        {tab === 'pedidos' && <PedidosTab />}
        {tab === 'pagamentos' && <PagamentosTab />}
        {tab === 'fornecedores' && <FornecedoresTab />}
        {tab === 'analise' && <AnaliseProjetoTab />}
        {tab === 'relatorio' && <RelatorioTab />}
        {tab === 'usuarios' && isAdmin && <UsuariosTab />}
      </div>
    </div>
  );
}
