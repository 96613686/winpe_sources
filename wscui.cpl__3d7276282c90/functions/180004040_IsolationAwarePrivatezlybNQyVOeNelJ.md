# IsolationAwarePrivatezlybNQyVOeNelJ

- ea: `0x180004040`
- end: `0x180004047`
- name: `IsolationAwarePrivatezlybNQyVOeNelJ`
- size: `7`
- prototype: `HMODULE __stdcall(LPCWSTR lpLibFileName)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180003e54`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180004040`

## pseudocode

```c
// attributes: thunk
HMODULE __stdcall IsolationAwarePrivatezlybNQyVOeNelJ(LPCWSTR lpLibFileName)
{
  return LoadLibraryW(lpLibFileName);
}

```

## disassembly

```asm
0x180004040  jmp     cs:__imp_LoadLibraryW
```
