# GdiAddInitialFontsThread

- ea: `0x180002710`
- end: `0x180002717`
- name: `GdiAddInitialFontsThread`
- size: `7`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `GDI32!GdiAddInitialFonts` at `0x180002710`

## pseudocode

```c
// attributes: thunk
__int64 GdiAddInitialFontsThread()
{
  return GdiAddInitialFonts();
}

```

## disassembly

```asm
0x180002710  jmp     cs:__imp_GdiAddInitialFonts
```
