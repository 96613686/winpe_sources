# memmove_0

- ea: `0x18002f3ae`
- end: `0x18002f3b4`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `36`
- callee_count: `0`
- tags: ``

## callers

- `0x180003340`
- `0x180003360`
- `0x180003380`
- `0x1800033a0`
- `0x1800033c0`
- `0x1800033e0`
- `0x180003420`
- `0x1800034a0`
- `0x180006598`
- `0x18000f670`
- `0x180012540`
- `0x180016520`
- `0x180017780`
- `0x18001e880`
- `0x18001ef00`
- `0x180020370`
- `0x180020670`
- `0x1800208e0`
- `0x180020ca0`
- `0x180021960`
- `0x1800230d0`
- `0x1800232c0`
- `0x1800261ac`
- `0x180026f90`
- `0x180029aa0`
- `0x180029b20`
- `0x180029c40`
- `0x180029db0`
- `0x180029ef0`
- `0x18002a240`
- `0x18002a750`
- `0x18002a840`
- `0x18002a8e0`
- `0x18002c73c`
- `0x18002cd9c`
- `0x18002d640`

## import_xrefs

- `msvcrt!memmove` at `0x18002f3ae`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove_0(void *a1, const void *Src, size_t Size)
{
  return memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x18002f3ae  jmp     cs:__imp_memmove
```
