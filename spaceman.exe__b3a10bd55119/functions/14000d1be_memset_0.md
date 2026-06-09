# memset_0

- ea: `0x14000d1be`
- end: `0x14000d1c4`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x140002074`
- `0x1400027dc`
- `0x140003620`
- `0x1400046f0`
- `0x140004958`
- `0x140004bf4`
- `0x1400054ac`
- `0x140005850`
- `0x140006834`
- `0x140008ad8`
- `0x140009e50`
- `0x14000a178`
- `0x14000b434`
- `0x14000c018`
- `0x14000c230`

## import_xrefs

- `msvcrt!memset` at `0x14000d1be`

## pseudocode

```c
// attributes: thunk
void *__cdecl memset_0(void *a1, int Val, size_t Size)
{
  return memset(a1, Val, Size);
}

```

## disassembly

```asm
0x14000d1be  jmp     cs:__imp_memset
```
