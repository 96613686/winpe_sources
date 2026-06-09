# memmove_0

- ea: `0x180026d3a`
- end: `0x180026d40`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `70`
- callee_count: `0`
- tags: ``

## callers

- `0x180002368`
- `0x180003590`
- `0x1800039f0`
- `0x180003c0c`
- `0x180003f10`
- `0x18000480c`
- `0x1800067f0`
- `0x180007a24`
- `0x18000881c`
- `0x1800094c0`
- `0x18000b560`
- `0x18000c024`
- `0x18000c4f0`
- `0x18000d454`
- `0x18000dbb8`
- `0x18000de34`
- `0x18000e528`
- `0x18000e7c8`
- `0x18000f688`
- `0x18000fa3c`
- `0x1800100f8`
- `0x180010c44`
- `0x1800148b4`
- `0x180015620`
- `0x180015e94`
- `0x1800160d0`
- `0x180016270`
- `0x180016340`
- `0x180016548`
- `0x180016904`
- `0x180016e70`
- `0x180017c60`
- `0x180018174`
- `0x180018240`
- `0x180018770`
- `0x180018f20`
- `0x1800191c0`
- `0x180019c90`
- `0x18001b118`
- `0x18001bbb8`
- `0x18001c318`
- `0x18001c77c`
- `0x18001cd64`
- `0x18001ce5c`
- `0x18001d074`
- `0x18001d19c`
- `0x18001d358`
- `0x18001dab0`
- `0x18001df44`
- `0x18001e398`

## import_xrefs

- `msvcrt!memmove` at `0x180026d3a`

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
0x180026d3a  jmp     cs:__imp_memmove
```
