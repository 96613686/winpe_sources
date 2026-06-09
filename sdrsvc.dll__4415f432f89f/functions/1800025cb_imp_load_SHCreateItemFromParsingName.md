# __imp_load_SHCreateItemFromParsingName

- ea: `0x1800025cb`
- end: `0x1800025d7`
- name: `__imp_load_SHCreateItemFromParsingName`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000254c`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x1800025cb`

## pseudocode

```c
__int64 load_SHCreateItemFromParsingName()
{
  return _tailMerge_api_ms_win_shell_namespace_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800025cb  lea     rax, __imp_SHCreateItemFromParsingName
0x1800025d2  jmp     __tailMerge_api_ms_win_shell_namespace_l1_1_0_dll
```
