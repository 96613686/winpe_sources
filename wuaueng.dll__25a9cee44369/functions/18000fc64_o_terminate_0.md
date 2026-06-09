# _o_terminate_0

- ea: `0x18000fc64`
- end: `0x18000fc6a`
- name: `_o_terminate_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180011a40`
- `0x180011b2c`
- `0x180011b98`
- `0x180012a9c`
- `0x180012f9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18000fc64`

## pseudocode

```c
// attributes: thunk
__int64 o_terminate_0()
{
  return _o_terminate();
}

```

## disassembly

```asm
0x18000fc64  jmp     cs:__imp__o_terminate
```
