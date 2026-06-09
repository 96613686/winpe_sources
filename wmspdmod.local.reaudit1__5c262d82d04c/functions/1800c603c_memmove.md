# memmove

- ea: `0x1800c603c`
- end: `0x1800c6042`
- name: `memmove`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x180085f44`
- `0x1800893cc`
- `0x18009c2b0`
- `0x18009c450`
- `0x18009deb8`
- `0x18009e768`
- `0x18009ff84`
- `0x1800af54c`
- `0x1800b3ef8`
- `0x1800b420c`
- `0x1800b92c8`
- `0x1800ba3a8`
- `0x1800bb570`
- `0x1800c5764`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x1800c603c`

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
0x1800c603c  jmp     cs:__imp_memmove
```
