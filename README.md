# 🧩 Tabs (ControllerTabs) Component

O componente `Tabs` (também exportado como `ControllerTabs`) é um componente React responsável por renderizar um conjunto de abas com conteúdos dinâmicos, utilizando `react-bootstrap`.

---

## ✨ Funcionalidades

- Renderização de múltiplas abas com títulos e conteúdos personalizados.
- Usa o componente `Tabs` do `react-bootstrap`.
- Suporte a seleção automática da primeira aba.
- Estilização customizada via SCSS.

---

## 🚀 Uso

### 1. **Importação do componente**

```tsx
import { Tabs } from "@/components/ControllerTabs/Tabs";
```

### 2. **Uso básico**

```tsx
<Tabs
  id="meu-conjunto-de-abas"
  tabList={[
    {
      id: "aba1",
      title: "Primeira Aba",
      content: <div>Conteúdo da Aba 1</div>,
    },
    {
      id: "aba2",
      title: "Segunda Aba",
      content: <div>Conteúdo da Aba 2</div>,
    },
  ]}
/>
```

---

## 📦 Props

| Propriedade | Tipo        | Descrição                                       |
|-------------|-------------|-------------------------------------------------|
| `id`        | `string`    | Identificador único do conjunto de abas        |
| `tabList`   | `TabType[]` | Lista de abas a serem renderizadas             |

### Estrutura de `TabType`

```ts
interface TabType {
  id: string;
  title: string;
  content: JSX.Element;
}
```

---

## 🎨 Estilo

- A classe `bg-white` é aplicada tanto nas abas quanto no conteúdo para fundo branco.
- Padding customizado é aplicado nas abas e no conteúdo.
- Estilos adicionais podem ser aplicados via `style.scss`.

---

## 📁 Estrutura de Arquivos

```
📦 components/ControllerTabs/
 ┣ 📜 Tabs.tsx
 ┣ 📜 style.scss
```

---

## 📌 Dependências

- `react`
- `react-bootstrap`
- `bootstrap` (CSS base)
- Estilos customizados (`style.scss`)

---

## 📝 Observações

- O componente não possui controle interno de estado ativo além da aba padrão.
- O `transition={false}` garante que não haja animações entre abas.
- Pode ser facilmente estendido para incluir ícones ou fechar abas dinamicamente.

---

## ✅ Exemplo Visual

```tsx
<Tabs
  id="exemplo-tabs"
  tabList={[
    {
      id: "info",
      title: "Informações",
      content: <InformacoesComponent />,
    },
    {
      id: "config",
      title: "Configurações",
      content: <ConfiguracoesComponent />,
    },
  ]}
/>
```

---

## 📞 Suporte

Para sugestões, melhorias ou bugs, entre em contato com o time de UI/UX ou frontend.
