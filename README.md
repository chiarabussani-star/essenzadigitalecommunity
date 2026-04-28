# Essenza Digitale Community

Una membership pensata per insegnanti yoga e operatori olistici per raggiungere più persone interessate ai loro servizi.

---

## Social Post Maker

Agente Claude che usa il server MCP di Canva per creare post social compilando automaticamente i template di brand.

### 1. Configurazione MCP (una-tantum)

Aggiungi il server Canva al tuo `claude_desktop_config.json`:

**Mac:** `~/Library/Application Support/Claude/claude_desktop_config.json`  
**Windows:** `%APPDATA%\Claude\claude_desktop_config.json`  
**Linux:** `~/.config/Claude/claude_desktop_config.json`

```json
{
  "mcpServers": {
    "canva": {
      "command": "npx",
      "args": ["-y", "@canva/mcp-server"],
      "env": {
        "CANVA_CLIENT_ID": "il-tuo-client-id",
        "CANVA_CLIENT_SECRET": "il-tuo-client-secret"
      }
    }
  }
}
```

Ottieni `CANVA_CLIENT_ID` e `CANVA_CLIENT_SECRET` creando un'app su [Canva Developers](https://www.canva.com/developers/apps).

Riavvia Claude Desktop dopo aver salvato il file.

### 2. Utilizzo

Una volta che il server MCP è attivo (icona 🔌 in Claude Desktop), usa questo prompt:

```
Sei il Social Post Maker di Essenza Digitale Community.

Argomento del post: [SCRIVI QUI IL TUO ARGOMENTO]

1. Usa canva_find_brand_templates per cercare i miei template di brand.
2. Scegli il template più adatto per un post social.
3. Genera un [Titolo] (max 8 parole, tono ispirazionale) e un [Testo] (max 3 frasi, rivolto a insegnanti yoga e operatori olistici).
4. Usa canva_autofill_design per compilare i campi [Titolo] e [Testo] nel template scelto.
5. Usa canva_export_design per ottenere il link al post completato.
6. Mostrami il [Titolo] e il [Testo] generati e il link al design Canva.
```

### Esempio

```
Argomento del post: meditazione mattutina per ricaricare l'energia
```

Claude cercherà i tuoi template, genererà il testo e restituirà il link al post Canva pronto da pubblicare.
