# 📧 Editor de Templates de E-mail

Uma ferramenta web intuitiva para criação, edição e exportação de templates HTML para e-mails. Desenvolvida para facilitar a criação de comunicações padronizadas com suporte a variáveis dinâmicas e emojis seguros.

> **Status:** ✅ Concluído e Funcional

## 🔗 Demonstração
👉 **[Acesse o Editor Online Aqui](https://gaelaleixo.github.io/Projetos_de_Eficiencia/)**

---

## 🖼️ Visualização

<img width="957" height="427" alt="Home-Site" src="https://github.com/user-attachments/assets/88ceedce-4a5b-46bb-9591-7a03048b9468" />


---

## 🚀 Funcionalidades Principais

Analisei o código e destaquei os pontos fortes da ferramenta:

* **Edição Rica (WYSIWYG):** Formatação de texto (negrito, itálico, listas) em tempo real.
* **Variáveis Dinâmicas:** Inserção rápida de marcadores como `[CSM]`, `[Nome da conta]` e `[Primeiro]` para automação de e-mail marketing.
* **Tratamento de Eventos:** Conversão automática da tag `[Bloco de Eventos]` para a sintaxe `{{LISTA_EVENTOS}}` na exportação.
* **Emojis Seguros:** Seletor de emojis integrado que converte os ícones para **Entidades Unicode HTML** (ex: `&#128522;`), garantindo que apareçam corretamente em qualquer cliente de e-mail (Outlook, Gmail, etc).
* **Gerador de Botões CTA:** Criação facilitada de botões de "Call to Action" com estilos inline (CSS embutido), essenciais para e-mail marketing.
* **Visualização vs. Código:** Alternância rápida entre o preview visual e o código HTML final.
* **Cópia Rápida:** Botão para copiar todo o código HTML gerado para a área de transferência.

---

## 🛠️ Tecnologias Utilizadas

O projeto foi construído utilizando tecnologias modernas e leves:

* **HTML5 & CSS3**: Estrutura e semântica.
* **JavaScript (Vanilla)**: Lógica de manipulação do DOM, `execCommand` para edição de texto e conversão de Unicode.
* **Tailwind CSS (CDN)**: Para estilização rápida, responsiva e moderna.
* **FontAwesome**: Para ícones da interface.
* **Google Analytics 4**: Para monitoramento de tráfego e uso da ferramenta.

---

## 💡 Como Usar

1.  **Escreva seu e-mail:** Use a área de edição principal para digitar o conteúdo.
2.  **Personalize:** Utilize a barra de ferramentas para formatar texto, adicionar listas ou inserir botões.
3.  **Adicione Variáveis:** Clique nos botões laterais (ex: `[Nome da conta]`) para inserir placeholders que serão substituídos pela sua ferramenta de disparo de e-mail.
4.  **Exporte:** Clique na aba **"Código Fonte"** para ver o HTML ou clique no botão **"Copiar Código HTML"** no topo para levar o código pronto para sua plataforma de envio.



Sanitização de CSS
Todo o CSS gerado para os botões e containers é feito inline (estilo direto na tag), que é a melhor prática para compatibilidade com serviços de e-mail (Gmail, Outlook).

✒️ Autor
Desenvolvido por Gael Aleixo.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/gael-aleixo-4946841a4/)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/GaelAleixo)

Copyright © 2024 - Todos os direitos reservados.

---

## 🧠 Detalhes Técnicos (Destaques)

### Conversão de Emojis
Para evitar que emojis "quebrem" em leitores de e-mail antigos, o sistema utiliza uma função que converte caracteres especiais para entidades numéricas HTML:

```javascript
function encodeToUnicodeEntities(str) {
    return Array.from(str).map(char => {
        const code = char.codePointAt(0);
        return code > 127 ? '&#' + code + ';' : char;
    }).join('');
}




