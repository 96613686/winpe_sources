# _free_base

- ea: `0x18000fc2a`
- end: `0x18000fc30`
- name: `_free_base`
- size: `6`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180011f70`
- `0x180011f98`
- `0x180012008`
- `0x18001568c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__free_base` at `0x18000fc2a`

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
0x18000fc2a  jmp     cs:__imp__o__free_base
```
