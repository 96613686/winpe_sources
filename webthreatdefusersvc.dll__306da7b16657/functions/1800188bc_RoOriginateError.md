# RoOriginateError

- ea: `0x1800188bc`
- end: `0x1800188c2`
- name: `RoOriginateError`
- size: `6`
- prototype: `__int64()`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x1800095ac`
- `0x180009640`
- `0x18000a210`
- `0x18000a2d0`
- `0x18000a3c0`
- `0x18000a650`
- `0x18000a760`
- `0x18000b000`
- `0x18000b140`
- `0x18000b270`
- `0x18000c780`
- `0x18000f7a0`
- `0x18000f840`
- `0x18000f8a0`
- `0x18000fbf0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800188bc`

## pseudocode

```c
// attributes: thunk
__int64 RoOriginateError()
{
  return __imp_RoOriginateError();
}

```

## disassembly

```asm
0x1800188bc  jmp     cs:__imp_RoOriginateError
```
