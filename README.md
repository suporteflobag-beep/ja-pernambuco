# FlôBag · JA Pernambuco

Perfil de emergência em QR Code para corredores. Uma pouch de corrida com um QR único costurado — quem escanear vê os dados que o dono preencheu e pode ligar ou mandar mensagem para o contato de emergência. **Sem login, sem senha.**

## Como funciona (visão do corredor)

1. A pessoa compra a FlôBag (pouch com o QR costurado).
2. Escaneia o QR → abre `#/e/CODIGO`.
3. Aparece: **"Sua FlôBag ainda não foi ativada"**.
4. Clica em **Ativar minha FlôBag** → recebe um **token de segurança** (mostrado uma única vez).
5. Anota / baixa o token, marca o checkbox e preenche:
   - Nome completo, apelido, cidade, grupo de corrida
   - Contato de emergência (nome + telefone)
   - Mensagem para quem ajudar
   - Dados médicos (opcional): alergias, tipo sanguíneo, **convênio**, medicamentos
6. Pronto. **O QR nunca muda.** Qualquer pessoa que escanear aquele QR passa a ver a ficha de emergência com os dados preenchidos.

## Como funciona (visão de quem encontra)

1. Escaneia o QR da pouch.
2. Vê a ficha: nome, cidade, grupo, número de peito e mensagem.
3. Botões grandes de **Ligar** e **Mensagem** para o contato de emergência.
4. Bloco de **Informações importantes** (alergias, tipo sanguíneo, convênio, medicamentos) — só aparece o que o dono preencheu e liberou.

## Editar depois

- No **mesmo QR**, é só escanear de novo e clicar em **"Tenho código + token"**, colando os dois.
- O token está no arquivo `.txt` que a pessoa baixou na ativação (ou anotado).
- **Sem o token, não é possível editar.** Não guardamos cópia.

## Geração dos QRs em lote (para a gráfica)

### 1. Gerar códigos no Supabase

No **SQL Editor**:

```sql
-- Gera N QRs virgens (troque o número)
select public.generate_flobags(3001);
