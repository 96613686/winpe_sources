# _wfsopen

- ea: `0x18008fc34`
- end: `0x18008fc3a`
- name: `_wfsopen`
- size: `6`
- prototype: `FILE *__cdecl(const wchar_t *FileName, const wchar_t *Mode, int ShFlag)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180079d74`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfsopen` at `0x18008fc34`

## pseudocode

```c
// attributes: thunk
FILE *__cdecl wfsopen(const wchar_t *FileName, const wchar_t *Mode, int ShFlag)
{
  return _wfsopen(FileName, Mode, ShFlag);
}

```

## disassembly

```asm
0x18008fc34  jmp     cs:__imp__wfsopen
```
