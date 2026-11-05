# Mixagem — Soundcraft Ui Auto-RTA & Master EQ

Aplicativo Web/PWA para calibração acústica e alinhamento das 31 bandas do Equalizador Gráfico (GEQ) do canal **Master** das mesas digitais **Soundcraft Ui12, Ui16 e Ui24R**.

🔗 **Acesse online:** [https://lukeluciano3.github.io/mixagem/](https://lukeluciano3.github.io/mixagem/)

---

## 🚀 Funcionalidades

- **100% no Navegador:** Funciona diretamente no smartphone ou PC sem necessidade de instalar aplicativos ou rodar servidores.
- **Modo Offline Completo (PWA):** Usa Service Worker para cachear todos os recursos. Funciona mesmo conectado no Wi-Fi da mesa Soundcraft (sem internet).
- **RTA em Tempo Real (Web Audio API):**
  - Desativa filtros automáticos de voz do celular (`echoCancellation: false`, `noiseSuppression: false`, `autoGainControl: false`).
  - Mapeia com precisão as 31 bandas de 1/3 de oitava padrão ISO (20 Hz a 20 kHz).
- **Curva Recomendada (Harman Live Sound House Curve):**
  - Equilibra o sistema com graves encorpados, médios lineares e agudos suaves.
  - Limite de ganho seguro de até **+3.0 dB** (proteção contra queima de falantes).
  - Atenuação de até **-9.0 dB** para eliminar nós e ressonâncias do ambiente.
- **Comunicação Direta WebSocket:**
  - Envia comandos diretamente para `ws://10.10.1.1` no protocolo nativo Soundcraft Ui (`m.eq.peak.l.*`, `m.eq.peak.r.*`, `m.eq.bypass`, `m.eq.linked`).

---

## 📱 Dica de Conexão no Celular (GitHub Pages)

Como o GitHub Pages opera em **HTTPS** e a mesa Soundcraft opera em rede local **WebSocket (`ws://10.10.1.1`)**, o navegador pode bloquear a conexão local por segurança (*Conteúdo Misto*).

Para liberar no **Google Chrome**:
1. Toque no ícone de configurações ao lado do endereço do site (ao lado do cadeado).
2. Abra **Configurações do site**.
3. Na opção **Conteúdo não seguro**, altere para **Permitir**.
4. Pronto! O site poderá se comunicar com a mesa.

---

## 🛠️ Arquivos do Projeto

- `index.html`: A aplicação completa (UI, RTA, Canvas, 31 faders e WebSocket).
- `sw.js`: Service Worker para funcionamento offline.
- `manifest.json`: Manifesto PWA para adicionar à tela inicial do celular.
