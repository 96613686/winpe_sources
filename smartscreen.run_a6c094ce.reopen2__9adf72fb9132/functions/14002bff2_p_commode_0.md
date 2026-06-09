# __p__commode_0

- ea: `0x14002bff2`
- end: `0x14002bff8`
- name: `__p__commode_0`
- size: `6`
- prototype: `int *__cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140026970`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__p__commode` at `0x14002bff2`

## pseudocode

```c
// attributes: thunk
int *__cdecl _p__commode_0()
{
  return __p__commode();
}

```

## disassembly

```asm
0x14002bff2  jmp     cs:__imp___p__commode
```
