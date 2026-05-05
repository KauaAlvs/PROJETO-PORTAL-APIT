# 🎓 Portal APIT - Sistema Web de Gestão Educacional

![Next.js](https://img.shields.io/badge/Next.js-14-black?style=for-the-badge&logo=next.js)
![Supabase](https://img.shields.io/badge/Supabase-Database-3ECF8E?style=for-the-badge&logo=supabase)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css)
![Vercel](https://img.shields.io/badge/Vercel-Deploy-black?style=for-the-badge&logo=vercel)
![HostGator](https://img.shields.io/badge/HostGator-SMTP-FFC107?style=for-the-badge&logo=hostgator)

O **Portal APIT** não é apenas um painel de cadastros; é o coração da operação educacional da instituição. Construído para ser rápido, seguro e escalável, ele automatiza a contagem de horas letivas, blinda a segurança de acessos corporativos e centraliza a comunicação entre Gestão, Professores e Jovens Aprendizes.

Desenvolvido para eliminar as planilhas manuais de presença, automatizar o disparo de e-mails institucionais e dar ao jovem aprendiz o controle total (Mobile-First) sobre sua jornada de horas.

---

## 🚀 Principais Funcionalidades (O Cérebro do Sistema)

### 1. 🔐 Controle de Acesso Baseado em Cargos (RBAC) e Validação de Domínio
O sistema gerencia três níveis rígidos de acesso: **Gestor (Admin), Professor e Jovem Aprendiz**. Possui uma trava inteligente no backend (Server Actions) que impede a criação de alunos que não possuam o e-mail corporativo obrigatório `@apitaprendiz.org.br`, garantindo que pessoas de fora não acessem o conteúdo da turma.

### 2. ⏱️ Motor Autônomo de Banco de Horas
Fim da contagem manual de horas. O sistema cruza os dados da tabela de `attendances` (chamadas) com a carga horária de cada `class` (aula). Quando um professor registra a presença, o motor calcula automaticamente as horas válidas daquele dia e atualiza em tempo real o banco de horas do jovem aprendiz.

### 3. 📧 Fluxo Transacional Customizado (SMTP HostGator)
O sistema não depende de e-mails genéricos. Ele se conecta via SMTP à infraestrutura oficial da instituição para disparar convites, boas-vindas e redefinição de senhas com a identidade visual da APIT. Todo clique no e-mail passa por um "Cérebro de Roteamento" (`/auth/callback`) que valida o token de segurança invisivelmente e redireciona o usuário para uma **Página Universal de Sucesso** ou para o fluxo de nova senha.

### 4. 📊 Dashboard Corporativo em Tempo Real
A página do Gestor possui métricas instantâneas sobre o volume de acessos. Através de uma integração nativa com o **Recharts**, o gestor pode cruzar os dados de um aluno com um clique e visualizar um gráfico de pizza gerado no servidor, ilustrando a taxa de Frequência Letiva (Presenças x Faltas) e a saúde do seu banco de horas.

### 5. 📱 Experiência Mobile-First Responsiva
Desenvolvido com Tailwind CSS, o layout mutante adapta tabelas complexas de gestão em "Cards" minimalistas nos smartphones. A navegação foi pensada para o toque (Touch-friendly), facilitando o check-in das chamadas pelo professor em sala de aula e a visualização rápida do aluno no transporte.

---

## 🛠️ Arquitetura e Tecnologias

- **Frontend/Backend:** Next.js 14 (App Router) + React Server Actions
- **Database / BaaS:** Supabase (PostgreSQL) + Row Level Security (RLS)
- **Autenticação:** Supabase Auth + SMTP HostGator Customizado
- **Gráficos e Análise:** Recharts
- **Estilização:** Tailwind CSS v4
- **Deploy & Hospedagem:** Vercel (com apontamento DNS personalizado)

