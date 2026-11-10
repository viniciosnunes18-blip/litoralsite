# Site Litoral Diesel

Site institucional da Litoral Diesel, assistência técnica autorizada Yanmar Marine em Angra dos Reis (RJ) e Salvador (BA).

É um projeto separado do sistema interno (Litoral Manage): tem repositório próprio e publicação própria no Cloudflare.

- `public/` traz o site inteiro (`index.html` e as logos), sem etapa de build.
- O Cloudflare publica sozinho a cada mudança na branch principal (Workers Builds: comando de deploy `npx wrangler deploy`).
- No formulário "Agendar atendimento", o pedido vai para `https://litoral-manage-backend.onrender.com/api/site/contato`, que avisa a equipe no sistema. Se a unidade tiver WhatsApp configurado (`WHATSAPP` no fim do `index.html`), a conversa também abre pronta.

## Domínio

Para usar `litoraldiesel.com.br`:
1. Leve o DNS do domínio da Locaweb para o Cloudflare, copiando antes as entradas de e-mail (MX, SPF/TXT).
2. Em Workers → `litoral-diesel-site` → Domains & Routes, adicione `litoraldiesel.com.br` e `www.litoraldiesel.com.br`.
