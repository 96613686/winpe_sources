# memmove_0

- ea: `0x18001a81d`
- end: `0x18001a823`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180003ac4`
- `0x180005b0c`

## import_xrefs

- `ntdll!memmove` at `0x18001a81d`

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
0x18001a81d  jmp     cs:__imp_memmove
```
