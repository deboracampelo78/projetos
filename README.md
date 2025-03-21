# 📚 WesSidebarMenu Component

O `WesSidebarMenu` é um componente React responsável por renderizar dinamicamente o menu lateral da aplicação com base nos dados retornados do backend. Ele integra-se com os contextos de autenticação, navegação e variáveis globais para controlar estados, navegação e breadcrumbs.

---

## ✨ Funcionalidades

- Geração dinâmica de menus e submenus via API.
- Suporte à navegação e execução de comandos.
- Atualização automática de breadcrumbs e estado da página.
- Acessibilidade com suporte a teclado (`Enter`, `ArrowUp`, `ArrowDown`).
- Suporte a comandos específicos enviados via API (`COMANDO` e `VISAO`).

---

## 🚀 Uso

### 1. **Importação do componente**

```tsx
import { WesSidebarMenu } from "@/components/SideBarMenu/WesSidebarMenu";
```

### 2. **Uso no layout**

```tsx
<WesSidebarMenu menuId="ID_DO_MENU" />
```

---

## ⚙️ Props

| Propriedade | Tipo     | Descrição                          |
|-------------|----------|------------------------------------|
| `menuId`    | `string` | ID do menu a ser carregado via API |

---

## 🧠 Como Funciona

1. **Carregamento do menu**
   - Ao montar, o componente chama `wesApi.getMenu(menuId)` com o token de autenticação.
   - O menu é armazenado no estado local e renderizado dinamicamente.

2. **Renderização**
   - Usa os componentes `SidebarMenuItem` e `SidebarMenuItemWithSub` para renderizar os itens.
   - Suporte a submenus aninhados.

3. **Navegação**
   - Clique ou `Enter` em um item executa a navegação.
   - Itens com `COMANDO` disparam chamadas para `wesApi.postMenuCommand`.

4. **Acessibilidade**
   - Teclas `ArrowUp` e `ArrowDown` movem o foco entre os itens.
   - `Enter` ativa o item focado.

---

## 📁 Estrutura de Arquivos

```
📦 components/SideBarMenu/
 ┣ 📜 WesSidebarMenu.tsx
 ┣ 📜 SideBarMenu.styles.ts
```

---

## 🔧 Integrações

- `AuthContext`: Para obter o token de acesso.
- `VariaveisGlobaisContext`: Para manipular estado e breadcrumbs.
- `WesNavigationContext`: Para navegar entre páginas.
- `wesApi`: Para obter menus e executar comandos.
- `useGetTasks`: Para controle de tarefas assíncronas.

---

## 🔌 Dependências

- `react-router-dom`
- `styled-components`
- `@/app/context/AuthContext`
- `@/app/context/WesNavigationContext`
- `@/app/context/hooks/VariaveisGlobaisContext`
- `@/app/modules/wes-replacement/apis/WesBackApi`

---

## 📝 Observações

- O componente espera que a API de menu retorne dados no formato esperado (`MenuModel`).
- Itens do menu com a propriedade `COMANDO` são tratados como ações executáveis, enquanto os que possuem `PAGINA` são tratados como links de navegação.
- É possível estender o componente para adicionar animações, ícones personalizados ou controle de permissões.

---

## ✅ Exemplo de Item de Menu

```json
{
  "id": "menu1",
  "name": "Relatórios",
  "properties": {
    "PAGINA": "relatorio-financeiro",
    "CLASSEICONE": "bi-bar-chart"
  },
  "items": []
}
```

Esse item será renderizado como um link para `/wespage/relatorio-financeiro`.

---

## 📞 Suporte

Para dúvidas ou sugestões, entre em contato com o time de desenvolvimento WES.
