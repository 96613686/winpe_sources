# memmove_0

- ea: `0x1800051ed`
- end: `0x1800051f3`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `24`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b0ec`
- `0x18000c4f4`
- `0x18000dc34`
- `0x18000f934`
- `0x180010800`
- `0x180012404`
- `0x18001395c`
- `0x180014400`
- `0x180017dc0`
- `0x18001eddc`
- `0x18002a104`
- `0x18002c1a0`
- `0x180043210`
- `0x180045abc`
- `0x180045af8`
- `0x180045bc0`
- `0x180046d54`
- `0x180046e34`
- `0x180046f18`
- `0x180047030`
- `0x180047350`
- `0x180048330`
- `0x180068eec`
- `0x18006bc1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x1800051ed`

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
0x1800051ed  jmp     cs:__imp_memmove
```
