# Teste



## Estrutura

```
Teste/
│   ├── index.html
│   │   ├── virtual-file-system-sem-erros.js
│   │   ├── filetree-sem-erros.js
│   │   ├── editor-principal-sem-erros.js
│   │   ├── estado.js
│   │   ├── main.js
│   │   ├── base.css
│   │   ├── header.css
│   │   ├── main.css
│   │   ├── sidebar.css
│   │   ├── filetree.css
│   │   ├── editor-main.css
│   │   ├── editor-container.css
│   │   ├── bottom-sheet.css
│   │   ├── scrollbar.css
│   │   ├── responsivo.css
│   ├── MAPA.md

```

## Arquivos

### index.html

**Tipo:** HTML

**Descrição:** N/A

**Linhas:** 100

```
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>SK Mini Editor - Completo</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<link rel="stylesheet" href="css/base.css">
<link rel="stylesheet" href="css/header.css">
<link rel="stylesheet" href="css/main.css">
<link rel="stylesheet" href="css/sidebar.css">
<link rel="stylesheet" href=
...
```

### virtual-file-system-sem-erros.js

**Tipo:** JavaScript

**Descrição:** N/A

**Linhas:** 225

```
/**
 * Módulo: virtual-file-system-sem-erros
 * Contém: MiniVFSRobusto
 * Usa de outros arquivos: function Object() { [native code] }.js (constructor)
 * Gerado pela Triagem de Código em 30/09/2026 a partir de bloco #2
 */

// ═══════════════════════════════════════════════════════════════════════════
class MiniVFSRobusto {
  constructor() {
    this.files = {};
    this.folders = new Set(['/']);
  }

  addFile(path, content) {
    try {
      if (!path || typeof path !== 'string') return false;
...
```

### filetree-sem-erros.js

**Tipo:** JavaScript

**Descrição:** N/A

**Linhas:** 119

```
/**
 * Módulo: filetree-sem-erros
 * Contém: MiniFileTree
 * Usa de outros arquivos: function Object() { [native code] }.js (constructor)
 * Gerado pela Triagem de Código em 30/09/2026 a partir de bloco #2
 */

// ═══════════════════════════════════════════════════════════════════════════
class MiniFileTree {
  constructor(containerId, vfs) {
    this.container = document.getElementById(containerId);
    this.vfs = vfs;
    this.expanded = new Set(['/']);
    this.onFileSelect = () => {};
    th
...
```

### editor-principal-sem-erros.js

**Tipo:** JavaScript

**Descrição:** N/A

**Linhas:** 287

```
/**
 * Módulo: editor-principal-sem-erros
 * Contém: MiniEditor
 * Usa de outros arquivos: function Object() { [native code] }.js (constructor); estado.js (miniVFS); filetree-sem-erros.js (MiniFileTree)
 * Gerado pela Triagem de Código em 30/09/2026 a partir de bloco #2
 */

// ═══════════════════════════════════════════════════════════════════════════
class MiniEditor {
  constructor() {
    try {
      this.currentFile = null;
      this.tabs = new Set();
      
      this.setupElements();
   
...
```

### estado.js

**Tipo:** JavaScript

**Descrição:** N/A

**Linhas:** 9

```
/**
 * Estado: variáveis e configurações compartilhadas
 * Contém: miniVFS
 * Usa de outros arquivos: virtual-file-system-sem-erros.js (MiniVFSRobusto)
 * Gerado pela Triagem de Código em 30/09/2026 a partir de bloco #2
 */

const miniVFS = new MiniVFSRobusto();

...
```

### main.js

**Tipo:** JavaScript

**Descrição:** N/A

**Linhas:** 11

```
/**
 * Início: código que roda quando a página abre (carregue por último)
 * Usa de outros arquivos: editor-principal-sem-erros.js (MiniEditor)
 * Gerado pela Triagem de Código em 30/09/2026 a partir de bloco #2
 */

// Inicializar
document.addEventListener('DOMContentLoaded', () => {
  window.miniEditor = new MiniEditor();
});

...
```

### base.css

**Tipo:** CSS

**Descrição:** N/A

**Linhas:** 30

```
/* base */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    :root {
      --bg-primary: #0d1117;
      --bg-secondary: #161b22;
      --border: #30363d;
      --text-primary: #c9d1d9;
      --text-secondary: #8b949e;
      --accent: #1f6feb;
    }

    body {
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto';
      background: var(--bg-primary);
      color: var(--text-primary);
      overflow: hidden;
    }

    .mini-editor-app {
    
...
```

### header.css

**Tipo:** CSS

**Descrição:** N/A

**Linhas:** 86

```
/* HEADER */
    .mini-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0.75rem 1rem;
      background: var(--bg-secondary);
      border-bottom: 1px solid var(--border);
      gap: 1rem;
    }

    .mini-header-left {
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .mini-header-left i {
      font-size: 1.25rem;
      color: #58a6ff;
    }

    .mini-header-left h1 {
      font-size: 1rem;
      font-weig
...
```

### main.css

**Tipo:** CSS

**Descrição:** N/A

**Linhas:** 9

```
/* MAIN */
    .mini-main {
      display: flex;
      flex: 1;
      overflow: hidden;
      gap: 1px;
      background: var(--border);
    }

...
```

### sidebar.css

**Tipo:** CSS

**Descrição:** N/A

**Linhas:** 29

```
/* SIDEBAR */
    .mini-sidebar {
      width: 250px;
      background: var(--bg-secondary);
      display: flex;
      flex-direction: column;
      overflow: hidden;
      border-right: 1px solid var(--border);
    }

    .mini-sidebar-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0.75rem 1rem;
      border-bottom: 1px solid var(--border);
    }

    .mini-sidebar-header h2 {
      font-size: 0.875rem;
      font-weight: 600;
    
...
```

### filetree.css

**Tipo:** CSS

**Descrição:** N/A

**Linhas:** 81

```
/* FILETREE */
    .mini-tree-folder,
    .mini-tree-file {
      display: flex;
      flex-direction: column;
    }

    .mini-tree-item {
      display: flex;
      align-items: center;
      gap: 0.5rem;
      padding: 0.5rem 0.75rem;
      cursor: pointer;
      transition: background 0.2s;
      border-left: 2px solid transparent;
    }

    .mini-tree-item:hover {
      background: rgba(255, 255, 255, 0.05);
    }

    .mini-tree-item.active {
      background: rgba(31, 111, 235, 0.1);
   
...
```

### editor-main.css

**Tipo:** CSS

**Descrição:** N/A

**Linhas:** 57

```
/* EDITOR MAIN */
    .mini-editor-main {
      flex: 1;
      display: flex;
      flex-direction: column;
      overflow: hidden;
    }

    .mini-tabs {
      display: flex;
      gap: 0.5rem;
      padding: 0.5rem 0.75rem;
      background: var(--bg-secondary);
      border-bottom: 1px solid var(--border);
      overflow-x: auto;
      overflow-y: hidden;
    }

    .mini-tab {
      display: flex;
      align-items: center;
      gap: 0.5rem;
      padding: 0.5rem 0.75rem;
      background:
...
```

### editor-container.css

**Tipo:** CSS

**Descrição:** N/A

**Linhas:** 92

```
/* EDITOR CONTAINER */
    .mini-editor-container {
      display: flex;
      flex: 1;
      overflow: hidden;
      gap: 1px;
      background: var(--border);
    }

    .mini-code-section {
      flex: 1;
      display: flex;
      flex-direction: column;
      overflow: hidden;
    }

    .mini-code-editor {
      flex: 1;
      padding: 1rem;
      background: var(--bg-primary);
      color: var(--text-primary);
      border: none;
      outline: none;
      font-family: 'Fira Code', 'Couri
...
```

### bottom-sheet.css

**Tipo:** CSS

**Descrição:** N/A

**Linhas:** 66

```
/* BOTTOM SHEET */
    .mini-bottom-sheet {
      position: fixed;
      inset: 0;
      z-index: 9999;
      display: flex;
      flex-direction: column;
    }

    .mini-sheet-overlay {
      flex: 1;
      background: rgba(0, 0, 0, 0.5);
      cursor: pointer;
    }

    .mini-sheet-content {
      background: var(--bg-secondary);
      border-top: 1px solid var(--border);
      border-radius: 1.5rem 1.5rem 0 0;
      overflow: hidden;
    }

    .mini-sheet-header {
      display: flex;
    
...
```

### scrollbar.css

**Tipo:** CSS

**Descrição:** N/A

**Linhas:** 19

```
/* SCROLLBAR */
    ::-webkit-scrollbar {
      width: 8px;
      height: 8px;
    }

    ::-webkit-scrollbar-track {
      background: transparent;
    }

    ::-webkit-scrollbar-thumb {
      background: var(--border);
      border-radius: 4px;
    }

    ::-webkit-scrollbar-thumb:hover {
      background: #484f58;
    }

...
```

### responsivo.css

**Tipo:** CSS

**Descrição:** N/A

**Linhas:** 13

```
/* RESPONSIVO */
    @media (max-width: 1024px) {
      .mini-preview-section {
        display: none;
      }
    }

    @media (max-width: 768px) {
      .mini-sidebar {
        width: 200px;
      }
    }

...
```

### MAPA.md

**Tipo:** Markdown

**Descrição:** N/A

**Linhas:** 69

```
# Mapa dos módulos

Gerado pela Triagem de Código em 30/09/2026, a partir de bloco #2.
Modo: Simples (arquivos carregados em ordem, abre com dois cliques).

## Quando algo quebrar

1. Abra a página, aperte F12 e veja a aba Console. O erro mostra o nome do arquivo e a linha.
2. Procure esse arquivo aqui embaixo para ver o que ele faz e do que depende.
3. Mande para a IA só esse arquivo e este MAPA, e peça: "Corrija só este arquivo e me devolva ele completo. Não mude nomes de funções nem de variáv
...
```

