# _o___std_exception_copy_0

- ea: `0x18002fde5`
- end: `0x18002fdeb`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x180008e1c`
- `0x18000a3dc`
- `0x18000fc14`
- `0x18000fc58`
- `0x180019fb0`
- `0x180021424`
- `0x180021ebc`
- `0x180022308`
- `0x180022368`
- `0x1800223c8`
- `0x18002241c`
- `0x18002db48`
- `0x18002dbc0`
- `0x18002dc3c`
- `0x18002dce0`
- `0x18002dd50`
- `0x18002ddbc`
- `0x180034d38`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x18002fde5`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_copy_0()
{
  return _o___std_exception_copy();
}

```

## disassembly

```asm
0x18002fde5  jmp     cs:__imp__o___std_exception_copy
```
