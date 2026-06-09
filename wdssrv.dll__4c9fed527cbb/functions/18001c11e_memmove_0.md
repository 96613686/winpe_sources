# memmove_0

- ea: `0x18001c11e`
- end: `0x18001c124`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x180002c24`
- `0x180003680`
- `0x1800049b4`
- `0x180005600`
- `0x180010048`
- `0x180010e90`
- `0x180011760`
- `0x1800123d8`
- `0x180012790`
- `0x180013fb8`
- `0x180014c24`
- `0x180015144`
- `0x1800162d4`
- `0x180018984`
- `0x180018b08`
- `0x180018cdc`
- `0x180019668`
- `0x18001b0cc`
- `0x18001b244`

## import_xrefs

- `msvcrt!memmove` at `0x18001c11e`

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
0x18001c11e  jmp     cs:__imp_memmove
```
