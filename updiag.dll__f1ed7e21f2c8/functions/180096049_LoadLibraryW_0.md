# LoadLibraryW_0

- ea: `0x180096049`
- end: `0x18009604f`
- name: `LoadLibraryW_0`
- size: `6`
- prototype: `HMODULE __stdcall(LPCWSTR lpLibFileName)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180062254`
- `0x180067d20`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180096049`

## pseudocode

```c
// attributes: thunk
HMODULE __stdcall LoadLibraryW_0(LPCWSTR lpLibFileName)
{
  return LoadLibraryW(lpLibFileName);
}

```

## disassembly

```asm
0x180096049  jmp     cs:__imp_LoadLibraryW
```
