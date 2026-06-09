# _free_base

- ea: `0x18000fbda`
- end: `0x18000fbe0`
- name: `_free_base`
- size: `6`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180011f20`
- `0x180011f48`
- `0x180011fb8`
- `0x18001563c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__free_base` at `0x18000fbda`

## pseudocode

```c
// attributes: thunk
void __cdecl free_base(void *Block)
{
  _o__free_base(Block);
}

```

## disassembly

```asm
0x18000fbda  jmp     cs:__imp__o__free_base
```
