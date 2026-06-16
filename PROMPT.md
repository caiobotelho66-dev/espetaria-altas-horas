No terminal, dentro da pasta do projeto, rode em sequência:



git init

git add .

git commit -m "site espetaria altas horas"

vercel



Quando o vercel perguntar:

\- Set up and deploy? → Y

\- Which scope? → escolha sua conta

\- Link to existing project? → N

\- Project name? → espetaria-altas-horas (ou enter pra aceitar o padrão)

\- In which directory is your code? → ./ (só enter)

\- Want to override settings? → N



Ele vai gerar uma URL de preview. Se quiser subir como produção definitiva rode depois:



vercel --prod

