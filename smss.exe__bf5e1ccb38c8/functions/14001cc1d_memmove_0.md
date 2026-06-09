# memmove_0

- ea: `0x14001cc1d`
- end: `0x14001cc23`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140019154`
- `0x140019244`
- `0x14001933c`
- `0x140019a5c`
- `0x14001ae48`
- `0x14001bb50`

## import_xrefs

- `ntdll!memmove` at `0x14001cc1d`

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
0x14001cc1d  jmp     cs:__imp_memmove
```
