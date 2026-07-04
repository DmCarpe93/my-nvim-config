# Neovim Tag / Symbol Navigation 정리

## 1. LSP 기반 (neovim 0.11 native — 기본 동작)

| 키 | 동작 |
|---|---|
| `gd` | go to definition |
| `gD` | go to declaration |
| `grr` | references |
| `gri` | implementation |
| `grt` | type definition |
| `grn` | rename |
| `K` | hover docs |

---

## 2. LSP User Commands

### clangd (`c`, `cpp` 파일)
| 커맨드 | 동작 |
|---|---|
| `:LspClangdSwitchSourceHeader` | `.h` ↔ `.cpp` 토글 |
| `:LspClangdShowSymbolInfo` | 심볼 정보 플로팅 창 |

### pyright (`python` 파일)
| 커맨드 | 동작 |
|---|---|
| `:LspPyrightOrganizeImports` | import 정리 |
| `:LspPyrightSetPythonPath <path>` | python 경로 변경 |

---

## 3. Telescope

### 현재 매핑된 것
| 키 | 동작 |
|---|---|
| `<leader>fh` | `help_tags` |

### 추가 가능한 LSP picker
```lua
mapKey('<leader>fs', builtin.lsp_document_symbols)   -- 현재 파일 심볼
mapKey('<leader>fw', builtin.lsp_workspace_symbols)  -- 워크스페이스 심볼
mapKey('<leader>fd', builtin.lsp_definitions)        -- 정의 목록
mapKey('<leader>fr', builtin.lsp_references)         -- 참조 목록
```

---

## 4. Vim 빌트인 ctags (ctags 별도 설치 시)

| 키 / 커맨드 | 동작 |
|---|---|
| `Ctrl-]` | tag jump |
| `Ctrl-t` | tag stack 뒤로 |
| `Ctrl-w ]` | 새 창에서 jump |
| `:tags` | tag stack 보기 |
| `:tnext` / `:tprev` | 다음 / 이전 tag |

> LSP가 있으면 ctags는 fallback 용도로만 쓰임.
