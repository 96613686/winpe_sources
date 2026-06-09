# _initterm_e_0

- ea: `0x18000395b`
- end: `0x180003961`
- name: `_initterm_e_0`
- size: `6`
- prototype: `int __cdecl(_PIFV *First, _PIFV *Last)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000361c`

## import_xrefs

- `api-ms-win-core-crt-l2-1-0!_initterm_e` at `0x18000395b`

## pseudocode

```c
// attributes: thunk
int __cdecl initterm_e_0(_PIFV *First, _PIFV *Last)
{
  return _initterm_e(First, Last);
}

```

## disassembly

```asm
0x18000395b  jmp     cs:__imp__initterm_e
```
