# _o___std_exception_copy_0

- ea: `0x18008f9ff`
- end: `0x18008fa05`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `24`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a378`
- `0x18000aa6c`
- `0x18000e1c8`
- `0x18000e20c`
- `0x18000e2ac`
- `0x18000e2f0`
- `0x180014e30`
- `0x180015208`
- `0x180015268`
- `0x1800152c8`
- `0x18001531c`
- `0x180016ae0`
- `0x180019014`
- `0x18001a1c0`
- `0x180066a8c`
- `0x180068988`
- `0x180068c68`
- `0x18006932c`
- `0x180076b64`
- `0x180078cc8`
- `0x180078d38`
- `0x180078dd0`
- `0x180078e3c`
- `0x1800944d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x18008f9ff`

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
0x18008f9ff  jmp     cs:__imp__o___std_exception_copy
```
