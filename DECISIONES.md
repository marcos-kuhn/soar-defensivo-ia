# Registro de decisiones

## D-001: Formato de evento genérico
- Fecha: 2026-10-12
- Decisión: todas las fuentes (Suricata, Wazuh y más adelante email)
  se traducen a un mismo formato antes de llegar al agente.
- Por qué: así puedo sumar fuentes nuevas (como el triage de phishing)
  sin tocar el agente; solo agrego un traductor.
- Alternativas descartadas: que el agente lea cada formato crudo
  (más frágil y más caro en tokens).

Formato:

    {
      "fuente": "suricata | wazuh | email",
      "tipo": "...",
      "timestamp": "...",
      "indicadores": { "ips": [], "urls": [], "hashes": [] },
      "raw": { }
    }

## D-002: Reparto de RAM del lab
- Fecha: 2026-10-12
- Decisión: VM SOC 8 GB, Kali 2 GB, Metasploitable2 512 MB.
- Por qué: mi PC tiene 16 GB y Windows necesita su parte.
- Plan B: bajar la VM SOC a 6 GB si el sistema se pone lento.

## D-003: Ubuntu Server 24.04 LTS en lugar de 26.04 LTS
- Fecha: 2026-10-12
- Decisión: usar 24.04 LTS para la VM del SOC.
- Por qué: el instalador all-in-one de Wazuh está verificado en 24.04;
  en 26.04 muestra una advertencia de sistema no soportado y hay que
  forzar la instalación.
- Alternativas descartadas: 26.04 LTS (más nueva, pero con menos
  garantías de compatibilidad para el lab).