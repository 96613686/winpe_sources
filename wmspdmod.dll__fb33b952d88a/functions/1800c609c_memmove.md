# memmove

- ea: `0x1800c609c`
- end: `0x1800c60a2`
- name: `memmove`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x180085fa4`
- `0x18008942c`
- `0x18009c310`
- `0x18009c4b0`
- `0x18009df18`
- `0x18009e7c8`
- `0x18009ffe4`
- `0x1800af5ac`
- `0x1800b3f58`
- `0x1800b426c`
- `0x1800b9328`
- `0x1800ba408`
- `0x1800bb5d0`
- `0x1800c57c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x1800c609c`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove(void *a1, const void *Src, size_t Size)
{
  return __imp_memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x1800c609c  jmp     cs:__imp_memmove
```
