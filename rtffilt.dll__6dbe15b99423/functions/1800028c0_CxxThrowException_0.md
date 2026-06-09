# _CxxThrowException_0

- ea: `0x1800028c0`
- end: `0x1800028c6`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x1800024b8`
- `0x180007390`
- `0x1800082cc`
- `0x18000a650`
- `0x18000a7a0`
- `0x18000a810`
- `0x18000b7a0`
- `0x18000c5ac`
- `0x18000c964`
- `0x18000da94`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x1800028c0`

## pseudocode

```c
// attributes: thunk
void __stdcall __noreturn CxxThrowException_0(void *pExceptionObject, _ThrowInfo *pThrowInfo)
{
  _CxxThrowException(pExceptionObject, pThrowInfo);
}

```

## disassembly

```asm
0x1800028c0  jmp     cs:__imp__CxxThrowException
```
